Setup
-----

Get the `CLIENT_ID` and `CLIENT_SECRET` from:

    https://www.strava.com/settings/api

Then, generate the URL

    echo https://www.strava.com/oauth/authorize?client_id=$CLIENT_ID&redirect_uri=http://127.0.0.1/&response_type=code&approval_prompt=force

Authorise the application, then record copy-paste the `?code=` query-string parameter as `CODE`.

HTTP `POST` this via:

    curl -d "client_id=$CLIENT_ID&code=$CODE&client_secret=$CLIENT_SECRET" -X POST https://www.strava.com/oauth/token

You can then parse the `access_token` using:

    $ curl [..] | jq -r .access_token

Links

  * https://developers.strava.com/docs/authentication/
