# Contributing to shuorv

## Install dependencies

### Use docker under any OS

For any OS which have installed docker, we provide a docker container to build the project.

First clone the code and then run
```shell script
docker run -it -v $(pwd)/:/shuorv shuorv-builder:latest bash
```
under the code path, and the build system is ready.

Note: If you want to view the waveform,
you still need a waveform viewer like `gtkwave` under your host os.
See below for installing suggestions.

### Ubuntu

Note: Add `sudo` if necessary

- Install `git`, [JDK8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) and [`sbt`](https://www.scala-sbt.org/)

  ```shell script
  apt install curl
  echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
  curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | apt-key add
  apt update && apt install git openjdk-8-jdk sbt
  ```

- Install `gtkwave` (you can skip this if you cannot or don't want to view the waveform)
  ```shell script
  apt install gtkwave
  ```
  
## Get the code

- Fork this repo under your own GitHub account.

- Clone it to your computer
  ```shell
  git clone https://github.com/<your GitHub username>/shuorv
  ```
  
## Create a new branch

You need to `new` a branch with a meaningful name and `checkout` it.

```shell script
git checkout -b <name>
```

## Do Some Coding

You can modify whatever you want!

## Run tests

Note: It is normal to take a very long time 
to download packages from maven 
when you run `sbt` on the project for 
the first time.
```shell script
sbt test
```

## Check the waveform

After run the tests, a `test_run_dir` will be generated under the project dictionary.

In its sub dictionaries, there would be `.vcd` files, you can open them with 
`gtkwave` or similar software to view the waveform generated by the test cases.

## Commit and push

```shell
git add <new file>
git commit -m "<a meaningful message>"
git push
```
## Create a pull request to this repo

If your code work as expected, and you want to contribute to the upstream repo, please
create a pull request to `shuosc/master`, and check if your code can pass all the tests.

We'll check the pull request now and then, you may also request a review manually if you like.
    
## Need help?
    
Feel free to [open an issue here](https://github.com/shuosc/shuorv/issues)!

