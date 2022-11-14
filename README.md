# heroku-google-application-credentials-buildpack
Generates a Google credential file based on Heroku Config Vars.

This is useful when using a package such as [@google-cloud/storage](https://www.npmjs.com/package/@google-cloud/storage) which loads credentials from a file instead of an environmental variable.

## Usage

1. Create Config Vars key `GOOGLE_CREDENTIALS` and paste the content of service account credential JSON file as is.
2.  Create a key under Config Vars `GOOGLE_APPLICATION_CREDENTIALS` and set a value as `google-credentials.json`.
3. Create Config Vars key `APNS_P8_KEY_FILE` and paste the content of p8 Key
4. Create a key under Config Vars `APNS_P8_KEY` and set value as `apns_p8_key_file.p8`

The script with generate a file called `google-credentials.json` and `apns_p8_key_file.p8` which holds the content from the step #1 and #3 above.

To add to your application, run:

```
heroku buildpacks:set https://github.com/buyersight/heroku-google-application-credentials-buildpack.git -a your-app-name
```
