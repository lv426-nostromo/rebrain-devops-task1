# Simple Nginx Fixer

Contains default nginx.conf file to play with or to restore the broken one

## Getting Started

Use this config file if you need to restore you nginx to default settings or need a start point to create your own custom nginx configuration file.

In order to use this config file and be amused with truly amazing default nginx greeting page available on your server's 80 port you need  nginx  to be installed on your local or remote machine, web browser and cup of coffee.  You can use any IDE or text editor (vim, nano, emacs, vscode, atom etc. ) if you need to make modifications to the file. 

### Prerequisites

* Centos (6, 7, 8)
* Nginx
* Incoming connections on TCP 80 port allowed by firewall

Assuming we are using Centos 7, use following command to install nginx on your machine with root privileges:

```
$ yum install -y nginx
$ systemctl start nginx
```

*Note: epel-release repository should be activated in prior*

### Installing

Clone the repository and get into the project directory:

```
$ git clone https://gitlab.rebrainme.com/electricinnerself_at_gmail_com/rebrain-devops-task1.git
$ cd rebrain-devops-task1/
```

## Usage

### To fix broken/messed  nginx.conf file

1. Backup your current nginx.conf file:

    ```
   $ mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.back
    ```

2. Copy the default nginx.conf from  this repository to conf directory of nginx:

    ```
    $ cp nginx.conf /etc/nginx.conf
    ```

3. Restart nginx daemon:

    ```
    $ systemctl restart nginx
    ```

### To modify configuration

```
$ cd rebrain-devops-task1/
$ vim nginx.conf
```

You can use any IDE or text editor to modify the file. Tested with:

* Vim
* Nano
* Emacs
* Visual Studio Code
* Atom

## Settings

Depending on your machine's CPU  adjust amount  of worker processes:

```
worker_processes auto;
```

Use simple formula: CPU cores = worker processes, or stick to default value - auto, nginx will figure out by its own how many processes should be started.

You can set  amount of working connections here:

```
events {
    worker_connections 1024;
}
```

More configuration examples available [here](https://www.nginx.com/resources/wiki/start/topics/examples/full/).

## Authors

* **Electric Inner Self** - electricinnerself@gmail.com

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License
