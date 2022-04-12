# Bonus

Choose your own easter bunny

- Choose an image on google

- Go to https://base64.guru/converter/encode/image and convert you image into ASCII


- Go to folder `cd DD2482-executable-tutorial/server_devops/`{{execute}}
- Open the code in a text editor like `vim hello.html`{{execute}}
- Type `i`{{execute}} to enter insert mode and change the following line add the your own `<ID of the image>` you picked and converted.

```html 
<img src="data:image/png;base64, <ID of the image> =="/>
```
- To save the file press `esc` to escape the insert mode and `:wq`{{execute}} to save the changes.

<br/><br/>
Rebuild the Rust server to display your own image by following the same instructions as in step 6:

- Make sure the old server is not running, use `docker stop rusty-server1`{{execute}} to be sure you may also check what containers are running using `docker ps -a`{{execute}}

- Rebuild the docker image with the latest changes.
`docker build . -t rusty-server`{{execute}}

- Run the docker image to create a new container instance.
`docker run -d -it -p 7777:7878 --rm --name rusty-server1 rusty-server`{{execute}}

Finally, go to `https://2887145477-7777-elsy04.environments.katacoda.com/` and you should see your own image.



