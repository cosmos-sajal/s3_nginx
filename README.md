# nginx as a proxy server for your public s3 buckets

#### How to setup?
##### Changes required in default.conf
- Change `base_s3_url` to your something like - `s3-ap-south-1.amazonaws.com`, which points to your region where the bucket is situated.
- Change `bucket_name` to the name of your bucket.

##### How to create a container for the same?
- Run `docker build -t mynginx_image1 .` in the root of the directory.
(This will create an image for the nginx).
- Run `docker run --name mynginx1 -p 80:80 -d mynginx_image1`, this will run the docker container in the detached mode, and you are done.


#### Example
- If your s3 uploaded file was earlier directed as `https://s3-ap-south-1.amazonaws.com/demo_bucket/image1.png`, now it can be proxy passed as
`localhost/image1.png`.
- You can change the server as per your domain.


#### References
- https://stackoverflow.com/questions/44639182/nginx-proxy-amazon-s3-resources
- https://www.digitalocean.com/community/tutorials/how-to-run-nginx-in-a-docker-container-on-ubuntu-14-04
