# Terraform Provider for Infoblox
 <img width="171" alt="capture" src="https://user-images.githubusercontent.com/36291746/39614422-6b653088-4f8d-11e8-83fd-05b18ca974a2.PNG">

## Requirements
* [Terraform](https://www.terraform.io/downloads.html) 0.11.x
* [Go](https://golang.org/doc/install) 1.9 (to build the provider plugin)
* [dep](https://github.com/golang/dep)
* CNA License need to be installed on NIOS

## Building the Provider
Clone repository to `$GOPATH/src/github.com/infobloxopen/terraform-provider-infoblox`.
```sh
$ mkdir -p $GOPATH/src/github.com/infobloxopen; cd $GOPATH/src/github.com/infobloxopen
$ git clone git@github.com:infobloxopen/terraform-provider-infoblox
```
Enter the provider directory and build the provider.
```sh
$ cd $GOPATH/src/github.com/infobloxopen/terraform-provider-infoblox
$ make build
```

## Using the Provider
If you're building the provider, follow the instructions to [install it as a plugin](https://www.terraform.io/docs/plugins/basics.html#installing-a-plugin). After the build is complete, copy the `terraform-provider-infoblox` binary into the same path as your terraform binary. After placing it into your plugins directory, run `terraform init` to initialize it.

## Developing the Provider
If you wish to work on the provider, you'll first need Go installed on your machine (version 1.9+ is required). You'll also need to correctly setup a `GOPATH`, as well as adding `$GOPATH/bin` to your `$PATH`.

To compile the provider, run `make build`. This will build the provider and put the provider binary in the `$GOPATH/bin` directory.
```sh
$ make build
...
$ $GOPATH/bin/terraform-provider-infoblox
...
```
To test the provider, you can simply run `make test`.
```sh
$ make test
```
## Features of Provider
* Creation of Network View in NIOS appliance
* Creation & Deletion of Network in NIOS appliance
* Allocation & Deallocation of IP from a Network
* Association & Disassociation of IP Address for a VM
* Creation and Deletion of A, CNAME, Host, and Ptr records

## Disclaimer
To use the provider for DNS purposes, a parent (i.e. zone) must already exist. The plugin does not support the creation of zones.
