# Self Made Tools

## Overview

`farpha-tools` is a collection of utilities for cybersecurity teams and CTF players, that I also personally use.

## Usage

### IP Lookup

Endpoint: `/lookupIP/{IP}`

- Example: `https://tools.farpha.com/lookupIP/8.8.8.8`

This endpoint performs an IP lookup using the `api.findip.net` service, retrieves detailed information, parses it into a shorter, more user-friendly format, and adds a clickable Google Maps link for the location.

### IP Defanging

Endpoint: `/defangIP/{IP}`

- Example: `https://tools.farpha.com/defangIP/8.8.8.8`

This endpoint defangs the provided IP address by replacing dots with `[.]`.

### URL Defanging

Endpoint: `/defangURL`

- Example: `https://tools.farpha.com/defangURL?url=https://google.com`

This endpoint defangs the provided URL by replacing dots with `[.]` and converting `http` to `hxxp`.

## Diagram

Below is a diagram illustrating how the IP lookup process works:

```mermaid
graph LR
    A[User] --> B[IPLookup Endpoint]
    B --> C[api.findip.net]
    C --> D[Full JSON Response]
    D --> E[Parse JSON Response]
    E --> F[Shortened JSON with Google Maps Link]
    F --> A
