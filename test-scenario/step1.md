## Create NodeJS and express API

The first step is to craete the API using NodeJS and an express server.

To achieve this, we must install node, npm and express. Run the following commands in the terminal:

```
sudo apt install nodejs

npm install -g npm@latest
```

Now check that node and npm are installed by running the following in the terminal:

```
node -v

npm -v
```

We can now move on to create our node project. In the root directory, create a folder `kubernetes-tutorial` and cd into this folder `cd kubernetes-tutorial`.

From here, initialize the node project by running `npm init`. You will be prompted to perform a number of steps, press enter continously to chose the default settings. At the end, type in `yes` to agree to these settings.

It is time to install express, do so by running `npm install express`. After the installation, assert that it is correctly installed by running `npm list`. The output should look accordingly:

```
kubernetes-tutorial@1.0.0 /root/kubernetes-tutorial
└── express@4.18.1
```

We have set the main file to be index.js, so create a file named index.js inside the kubernetes-test directory. Insert the following code in index.js to setup the express server and API endpoints:

```
var express = require('express');
var app = express();

app.get('/', function (req, res) {
    res.status(200).send({
        success: true,
    });
});

app.get('/hello', function (req, res) {
    res.send({
        success: true,
        response: 'hello world'
    });
});

app.listen(process.env.PORT || 3001);
module.exports = app;
```

Next, we will craete a dockerfile and push it to Docker Hub.