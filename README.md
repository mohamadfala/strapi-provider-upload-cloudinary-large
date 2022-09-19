# strapi-provider-upload-cloudinary


[![NPM](https://img.shields.io/npm/v/strapi-provider-upload-cloudinary-large.svg)](https://www.npmjs.com/package/strapi-provider-upload-cloudinary-large) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)


## Upload large files support

This is a fork from the original strapi cloudinary plugin, modified to support uploading large files to cloudinary.
> You need to make sure your cloudinary plan supports larger files upload as well.


## Configurations

Your configuration is passed down to the cloudinary configuration. (e.g: `cloudinary.config(config)`). You can see the complete list of options [here](https://cloudinary.com/documentation/cloudinary_sdks#configuration_parameters)

`actionOptions` are passed directly to the upload and delete functions respectively allowing for custom options such as folder, type, etc. You can see the complete list of upload options [here](https://cloudinary.com/documentation/image_upload_api_reference#upload_optional_parameters) and delete options [here](https://cloudinary.com/documentation/image_upload_api_reference#destroy_optional_parameters)

See the [using a provider](https://strapi.io/documentation/developer-docs/latest/development/plugins/upload.html#using-a-provider) documentation for information on installing and using a provider. And see the [environment variables](https://strapi.io/documentation/developer-docs/latest/setup-deployment-guides/configurations.html#environment-variables) for setting and using environment variables in your configs.

**Example**

`./config/plugins.js`

```js
module.exports = ({ env }) => ({
  // ...
  upload: {
    provider: 'cloudinary',
    providerOptions: {
      cloud_name: env('CLOUDINARY_NAME'),
      api_key: env('CLOUDINARY_KEY'),
      api_secret: env('CLOUDINARY_SECRET'),
    },
    actionOptions: {
      upload: {},
      delete: {},
    },
  },
  // ...
});
```

## Resources

- [License](LICENSE)

## Links

- [Strapi website](https://strapi.io/)
- [Strapi community on Slack](https://slack.strapi.io)
- [Strapi news on Twitter](https://twitter.com/strapijs)
