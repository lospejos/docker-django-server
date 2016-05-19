# Run Django

`python manage.py runserver 8080`

# This application requires the docker ext client

https://github.com/savelee/docker-ext-client

You will need to edit the *client/app/utils/Contants.js* file to:
<pre>
Ext.define('Client.utils.Constants', {
    singleton: true,

    'LIVE_URL': window.location.protocol + "//" + window.location.host + ':8080',

    'TOKEN_PREFIX': 'JWT',
    'DISABLE_TOKEN': false
});
</pre>

# Visit Sencha client app and login:

1. `sencha app watch`
2. Open your browser, and browse to: http://127.0.0.1:1841
3. Login with your admin account

# Here's the docker-compose.yml

Make a sencha production build first:
`sencha app build`

<pre>
TODO
</pre>
