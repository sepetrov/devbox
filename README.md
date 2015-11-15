# DEVBOX - PHP-FPM/Nginx/MySQL Virtual Machine


The boilerplate for congifuring a virutal machine for web development.

Details:
* OS: Ubuntu Server 14.04 (Trusty Tahr)
* Packages:
    * PHP-FPM 5.6
    * MySQL 5.6
    * Nginx 1.8.0

The VirtualBox virtual machine is build using Vagrant and provisioned with
Ansible.

## Prerequisites

* [Ansible](http://www.ansible.com/)
* [Vagrant](http://vagrantup.com/)
* [VirtualBox](https://www.virtualbox.org/)

## Usage

From the root of this project, run

    $ vagrant up

## License

See [LICENSE](LICENSE).

## Author

[Stanislav Petrov](https://github.com/sepetrov)
