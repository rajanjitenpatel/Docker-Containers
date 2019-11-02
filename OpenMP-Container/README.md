# OpenMP-Container

1. Docker Platform: 

    - (Recommended) Online Ubuntu Playground with Docker Installed - [link](https://www.katacoda.com/courses/ubuntu/playground) (Open in new tab)

        OR

    - Install Docker on PC - [link](https://docs.docker.com/v17.09/engine/installation/#supported-platforms).
  
2. Run following commands.

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
      $ docker pull rjprime/openmp_container:0.1
      ```
          ```
          22e816666fd6: Pull complete
          079b6d2a1e53: Pull complete
          11048ebae908: Pull complete
          c58094023a2e: Pull complete
          e736effe5a80: Pull complete
          Digest: sha256:a66537788e7a2bba18d3b7c591b1d35e00efc85a785528cc2f23e7c7d50811a5
          Status: Downloaded newer image for rjprime/openmp_container:0.1
          ```
    d. View Docker images
      ```
      $ docker images
      ```
          ```
          REPOSITORY                   TAG                 IMAGE ID            CREATED             SIZE
          -> rjprime/openmp_container    0.1              1b785c33c7ae        13 minutes ago      201MB*
          redis                       latest              857c4ab5f029        2 months ago        98.2MB
          weaveworks/scope            1.11.4              a082d48f0b39        2 months ago        78.5MB
          ubuntu                      latest              3556258649b2        3 months ago        64.2MB
          alpine                      latest              b7b28af77ffe        3 months ago        5.58MB
          ```
    e. Run image  
      ```
      $ docker run -i -t rjprime/openmp_container:0.1 /bin/bash
      ```
          ```
          root@d395406b695e:/#
          ```
    f. List file & Dir. ( sum.c & a.out should be present.) 
      ```
      root@d395406b695e:/# ls
      ```
          ```
          "a.out"  boot  etc   lib    media  "openmp_sample.c"  proc  run   srv  tmp  var
          bin    dev   home  lib64  mnt    opt              root  sbin  sys  usr
          ```
    g. Run executable file.
      ```
      root@d395406b695e:/# gcc -fopenmp openmp_sample.c
      ```
          ```
          _
          ```
    h. Run executable file.
      ```
      root@d395406b695e:/# ./a.out
      ```
          ```
          Welcome to GFG from thread = 0
          Number of threads = 2
          Welcome to GFG from thread = 1
          ```
    i. To check code 
      ```
      root@d395406b695e:/# nano openmp_sample.c
      ```
          ```
          #include <stdio.h>
          #include <stdlib.h>
          #include <omp.h>
          .....
          .....
          ```



-- END --
      
      
