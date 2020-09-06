# WooCommerce Memberships REST API documentation

Official repository for the documentation of the [WooCommerce Memberships](https://woocommerce.com/products/woocommerce-memberships/) REST API.

[Follow this link](https://skyverge.github.io/woocommerce-memberships-rest-api-docs/) to read the **REST API documentation**. 

> If you are looking for the general **plugin documentation**, [please follow this link](https://docs.woocommerce.com/document/woocommerce-memberships/).
  
## Contributing

You can contribute to this documentation by:

* [Opening an issue](https://github.com/skyverge/woocommerce-memberships-rest-api-docs/issues/new) to report a problem or information missing, etc.
* Opening a pull request to extend the documentation.

> Please **do not submit feature requests or support requests for the REST API** here. You can use the [WooIdeas board](http://ideas.woocommerce.com/forums/133476-woocommerce?category_id=125014) or [Contact SkyVerge support](https://www.skyverge.com/support/).

## Running locally

### Vagrant

```shell
bundle install
```

> **Important note:** if you run into `bundle install` errors, you may need to install `ruby-devel` and install the related gems again to build native extensions.  

Then, to test changes locally run:

```shell
bundle exec middleman server
```

### Docker

1. Build the docker image:
    ```shell
    docker build . -t docs
    ```
1. Start the image:
    ```shell
    docker run -d --rm --name docs -p 4567:4567 -v $(pwd)/build:/srv/docs/build -v $(pwd)/source:/srv/docs/source docs
    ```

You will be able to access your site at http://localhost:4567.

To build your sources while the container is running, run:
```shell
docker exec -it docs /bin/bash -c "bundle exec middleman build"
```

## Updating pages

This project uses [Slate](https://github.com/lord/slate) for building the documentation pages.

Follow [Slate readme](https://github.com/lord/slate/blob/master/README.md) and [wiki](https://github.com/lord/slate/wiki) for instructions on how to edit files and make changes.

## Deploying an update 

After pushing changes and you are ready to deploy use the script:

```shell
bash deploy.sh
```
