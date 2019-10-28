# SIMD_Container
Experiment with docker container.


1. Go to: A Ubuntu Playground with Docker Install - [link](https://www.katacoda.com/courses/ubuntu/playground){:target="_blank"}

2. Run following command

    a. Check docker version 
      ```
      $ docker -v
      ```
          ```
          Docker version 18.09.7, build 2d0083d
          ```
     
    b. View Docker images 
      ```
      $ docker images
      ```
          ```
          REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
          redis               latest              857c4ab5f029        2 months ago        98.2MB
          weaveworks/scope    1.11.4              a082d48f0b39        2 months ago        78.5MB
          ubuntu              latest              3556258649b2        3 months ago        64.2MB
          alpine              latest              b7b28af77ffe        3 months ago        5.58MB
          ```
    c. Download SIMD image 
      ```
      $ docker pull rjprime/rjprime-simd
      ```
          ```
          Using default tag: latest
          latest: Pulling from rjprime/rjprime-simd
          22e816666fd6: Pull complete
          079b6d2a1e53: Pull complete
          11048ebae908: Pull complete
          c58094023a2e: Pull complete
          c7c0268dd4d0: Pull complete
          Digest: sha256:d98a7f598ddbc236c08b5a5dc73446d63922a24920e5aba83ccd3bc23cc78e68
          Status: Downloaded newer image for rjprime/rjprime-simd:latest
          ```
    d. View Docker images
      ```
      $ docker images
      ```
          ```
          REPOSITORY             TAG                 IMAGE ID            CREATED             SIZE
          -> rjprime/rjprime-simd   latest              1b785c33c7ae        13 minutes ago      201MB*
          redis                  latest              857c4ab5f029        2 months ago        98.2MB
          weaveworks/scope       1.11.4              a082d48f0b39        2 months ago        78.5MB
          ubuntu                 latest              3556258649b2        3 months ago        64.2MB
          alpine                 latest              b7b28af77ffe        3 months ago        5.58MB
          ```
    e. Run image  
      ```
      $ docker run -i -t rjprime/rjprime-simd /bin/bash
      ```
          ```
          root@d395406b695e:/#
          ```
    f. List file & Dir. ( sum.c & a.out should be present.) 
      ```
      root@d395406b695e:/# ls
      ```
          ```
          "a.out"  boot  etc   lib    media  opt   root  sbin  "sum.c"  tmp  var
          bin    dev   home  lib64  mnt    proc  run   srv   sys    usr
          ```
    g. Run executable file.
      ```
      root@d395406b695e:/# ./a.out
      ```
          ```
          sum = 120000
          Time elpased is 0.000203 seconds for naive sum.
          sum = 120000
          Time elpased is 0.000076 seconds for 128bit vectorize sum
          2.671053 X time faster.
          ```
    h. To check code 
      ```
      root@d395406b695e:/# nano sum.c
      ```
          ```
          #include <stdio.h>
          #include <smmintrin.h>
          #include <immintrin.h>
          #include <time.h>
          #include <unistd.h>
          #include <stdlib.h>
          .....
          .....
          ```



-- END --
      
      
