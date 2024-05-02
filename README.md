# DNS Configuration Documentation

## Overview

This repository contains a Terraform configuration file (`dns.tf`) that manages DNS records on DigitalOcean. Below is an explanation of how the `dns.tf` file works and what it does.

## File Description

The `dns.tf` file is responsible for defining DNS records for a domain hosted on DigitalOcean. It utilizes Terraform to automate the creation and management of these records.

## Contents

### dns.tf

The `dns.tf` file contains the following code:

```hcl
resource "digitalocean_record" "www" {
  domain = var.domain_name
  type = "A"
  name = "@"
  value = digitalocean_droplet.web.ipv4_addresss
}
