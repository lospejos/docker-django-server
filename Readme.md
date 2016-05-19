# This application requires the dockerextnode client

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
client:
    build: ./client
    restart: always
    ports:
      - "80:80"
    links:
      - server
server:
    build: ./server
    restart: always
    ports:
     - "9000:9000"
    links:
     - mongo
mongo:
  image: mongo
  command: --smallfiles
  restart: always
  ports:
    - "27017:27017"
</pre>
