# My public key

This repository is used to install my user and public key on a server.

## 1. Usage

### 1.1 Create my user with admin rights

```bash
root$ adduser --gecos "Björn Hempel" --gid 100 --disabled-password bjoern
root$ groupadd bjoern
root$ usermod bjoern -g users -G bjoern,sudo -p $(openssl passwd -1 -salt shaker "$password")
```

### 1.2 Install my public key

```bash
root$ cd /home/bjoern
root$ git clone git@github.com:bjoern-hempel/my-public-key.git
root$ cd my-public-key
root$ ./install bjoern
This will install the public key to user "bjoern".
The public key will be installed at: /home/bjoern/.ssh/authorized_keys

Do you want to continue? Type y(es) or n(o): y


install public key
done...
root$ cd ..
root$ rm -r my-public-key
```

## A. Authors

* Björn Hempel <bjoern@hempel.li> - _Initial work_ - [https://github.com/bjoern-hempel](https://github.com/bjoern-hempel)

## B. License

This library is licensed under the MIT License - see the [LICENSE.md](/LICENSE.md) file for details
