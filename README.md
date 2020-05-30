# Vanilla Express Demo
> Securely serve your content for Web Monetization users without depending on the ILP stack

- [How it Works](#how-it-works)
- [Installation and Setup](#installation-and-setup)

Using [Web Monetization](https://github.com/interledger/rfcs/blob/master/0028-web-monetization/0028-web-monetization.md), you often want to detect whether a visitor to your site is paying for the content.
 
The only way to guarantee that is by having a service that actually accepts Interledger packets and communicates to your backend.

Vanilla Express Demo uses *Vanilla Service* to validate payments and provide Web Monetization features and analytics.

The interaction between the Express Server and Vanilla Service is provided by the API.

## How it Works

1. First, the visitor arrives on your page.
  - If you detect the web monetization API on the client side, you can tell the visitor that the page is loading until monetization completes.
  - If the visitor does not have the web monetization API, you can send them to the non-monetized version of your site.
  
2. User sends request for specific content that is protect by Web Monetization
  - If the Express Server validates payment successfully, the visitor receives content
  - If the Express Server does not validate payment, the visitor receives error or non-monetized version

2. Add a Web Monetization meta tag pointing to the address generated by Vanilla Service (available in the Admin panel).

3. The visitor opens a connection to the Vanilla Service.

### Installation and Setup

First, install dependencies.

```shell
    yarn install
```

Start the server. (port 3000)
```shell
yarn start
```

Go to `localhost:3000/`.