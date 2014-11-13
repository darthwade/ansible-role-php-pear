# Ansible Role: PHP PEAR [![Build Status](https://travis-ci.org/darthwade/ansible-role-php-pear.png)](https://travis-ci.org/darthwade/ansible-role-php-pear)

Ansible role that installs PHP PEAR and its libraries/extensions.

Features include:
- Installation of PHP PEAR and it's dependencies
- Basic configuration
- Installation of PHP PEAR libraries/extensions

## Installation

Using `ansible-galaxy`:
```shell
$ ansible-galaxy install darthwade.php-pear
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):
```shell
$ arm install darthwade.php-pear
```

Using `git`:
```shell
$ git clone https://github.com/darthwade/ansible-role-php-pear.git
```

## Requirements & Dependencies
- Ansible 1.4 or higher
- PHP

## Variables
Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
# The PEAR channels that should be discovered so pear libraries can be installed. By default, PEAR is not configured to
# autodiscover channels for libraries you would like installed, so you need to explicitly list all the libraries' channels here.
php_pear_channels:
  - pear.phpunit.de
  - pear.symfony.com

# The libraries/extensions you would like installed via PEAR.
php_pear_libraries:
  - phpunit/PHPUnit
  - PHP_CodeSniffer
```

## Example playbook
```yaml
- hosts: all
  vars:
    php_pear_channels:
    - pear.phpunit.de
    php_pear_libraries:
    - phpunit/PHPUnit
  roles:
    - darthwade.php-pear
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Licensed under the MIT License. See the LICENSE file for details.
Copyright (c) 2014 [Vadym Petrychenko](http://petrychenko.com/)