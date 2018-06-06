# AVL GPU CLOUD QUICK-START

Login with your 4 digits ID (6210 is an example)
https://cn.portal.availink.com:6210/vnc.html

### copy example "models" from /home/public folder to local
```bash
$ cd $HOME
$ mkdir -p mygit
$ cp /home/public/mygit/models mygit/.
```

### start avlcloud/tf-horovod docker
```bash
$ docker run -it --network=host --pid=host \
-v /home/public/tensorflow/tf.record:/home/ubuntu/tf.record \
-v $HOME/mygit:/home/ubuntu/mygit \
--name my-tf-horovod --rm --privileged \
avlcloud/tf-horovod:latest
```
