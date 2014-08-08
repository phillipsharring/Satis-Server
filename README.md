# Satis-Server

A sample Satis Server setup.

## Installation

### Git

```bash
$ git clone git@github.com:philsown/Satis-Server.git Satis-Server
$ cd Satis-Server
$ php composer.phar install -o
```

### Composer

Add something like this to your `composer.json` file.

```json
{
    "repositories": [
        {
            "url": "https://github.com/philsown/Satis-Server.git",
            "type": "git"
        }
    ],
    "require": {
        "philsown/Satis-Server": "dev-master"
    }
}
```	

## Configuration

### HTPASSWD

Create an `.htpasswd` file to protect your dist directory.

```bash
$ htpasswd -c .htpasswd composer
# enter password here
```

### HTACCESS

Edit the `.htaccess` file in `public/dist` to have the correct path to the `.htpasswd` file you created above.

```bash
$ cd public/dist
$ vi .htaccess
# edit the path
```

### Satis.json

Edit the `satis.json` and customize the values. In particular, modify the `repositories` key to list the repositories you would like to host on your package server.

```json
    "repositories": [
        {
            "type": "git",
            "url": "git@github.com:your-company/your-private-repo.git"
        }
    ],
```

## Usage

Make the `satis-rebuild` script in the bin folder executable, then run it.

```bash
$ chmod +x bin/satis-rebuild
$ bin/satis-rebuild
```

## Troubleshooting

### Can't connect to my private repo

Try to connect from the command line first, and resolve any issues with git config or ssh keys.

## I Made This

Author:  [Phillip Harrington](http://www.phillipharrington.com/).