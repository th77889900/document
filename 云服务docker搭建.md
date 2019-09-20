### docker容器搭建

  先安装yum，安装完成后通过yum安装docker
    $: yum install docker
    $: docker ps
    docker images
    docker run --name es-head -p 9100:9100 -d docker.io/mobz/elasticsearch-head:5
    
