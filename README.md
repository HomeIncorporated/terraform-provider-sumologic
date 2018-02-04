Terraform Provider
==================


Requirements
------------

-	[Terraform](https://www.terraform.io/downloads.html) 0.10.x
-	[Go](https://golang.org/doc/install) 1.9 (to build the provider plugin)

Building The Provider
---------------------

Clone repository to: `$GOPATH/src/github.com/brandonstevens/terraform-provider-sumologic`

```sh
$ mkdir -p $GOPATH/src/github.com/brandonstevens; cd $GOPATH/src/github.com/brandonstevens
$ git clone git@github.com:brandonstevens/terraform-provider-sumologic
```

Enter the provider directory and build the provider

```sh
$ cd $GOPATH/src/github.com/brandonstevens/terraform-provider-sumologic
$ make build
```

Using the provider
----------------------
If you're building the provider, follow the instructions to [install it as a plugin.](https://www.terraform.io/docs/plugins/basics.html#installing-a-plugin) After placing it into your plugins directory,  run `terraform init` to initialize it.

Developing the Provider
---------------------------

If you wish to work on the provider, you'll first need [Go](http://www.golang.org) installed on your machine (version 1.9+ is *required*). You'll also need to correctly setup a [GOPATH](http://golang.org/doc/code.html#GOPATH), as well as adding `$GOPATH/bin` to your `$PATH`.

To compile the provider, run `make build`. This will build the provider and put the provider binary in the `$GOPATH/bin` directory.

```sh
$ make build
...
$ $GOPATH/bin/terraform-provider-sumologic
...
```

In order to test the provider, you can simply run `make test`.

*Note:* Make sure `SUMOLOGIC_AUTH_TOKEN` and `SUMOLOGIC_ENDPOINT_URL` variables are set.

```sh
$ make test
```

In order to run the full suite of Acceptance tests, run `make testacc`.

*Note:* Make sure `SUMOLOGIC_AUTH_TOKEN` and `SUMOLOGIC_ENDPOINT_URL` variables are set.

*Note:* If you do not have a Sumo Logic account, you can create one and use the free tier.

```sh
$ make testacc
```