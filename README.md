# PythonAnywhere Terraform Provider

See the [PythonAnywhere API documentation](https://help.pythonanywhere.com/pages/).

## How to use
1. Install [Terraform](https://www.terraform.io/downloads.html) 1.2.5
2. Install [Go](https://golang.org/doc/install) 1.18.4 (to build the provider plugin)
3. Add the provider block to your terraform config
```
# Configure the PythonAnywhere Provider
provider "pythonanywhere" {
  version   = "~> 0.1"
  username  = "YOUR_API_TOKEN"
  api_token = "YOUR_USERNAME"
}

```
4. Set your API token and username as environment variables
  a. Set these environment variables or 
  ```
    export PYTHONANYWHERE_API_TOKEN="YOUR_API_TOKEN"
    export PYTHONANYWHERE_USERNAME="YOUR_USERNAME"
  ```
  b. or set them directly in terraform configuration:
  ```
  # For example, restrict provider version in 0.1.x
  provider "pythonanywhere" {
    version   = "~> 0.1"
    username  = "YOUR_API_TOKEN"
    api_token = "YOUR_USERNAME"
  }
  ```

## Building The Provider

1. `git clone ...`
2. `cd ...`
3. `make build`


## Developing

To compile the provider, run `make build`. 
  * This will build the provider and put the provider binary in the `$GOPATH/bin` directory.

## Testing
In order to test the provider, you can simply run `make test`.

In order to run the full suite of Acceptance tests, run `make testacc`.
  *Note:* Acceptance tests create real resources, and often cost money to run.