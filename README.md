# buildpack-google-app-creds
Generates a Google credential file based on Heroku Config Vars.

This is useful when using a package such as [@google-cloud/storage](https://www.npmjs.com/package/@google-cloud/storage) which loads credentials from a file instead of an environmental variable.

## Usage

1. Create Config Vars key `GOOGLE_CREDENTIALS` and paste the content of service account credential JSON file as is.
1. Create a key under Config Vars `GOOGLE_APPLICATION_CREDENTIALS` and set a value as `google-credentials.json`.

The script with generate a file called `google-credentials.json` which holds the key from the step #1 above.

To add to your application, run:

```
heroku buildpacks:set https://buildio/buildpack-google-app-creds -a your-app-name
```

## Warning

Storing credentials in plain text is not recommended. This buildpack update is for convenience and should not be used in production environments.
