Humus PHPUnit Module
====================

Humus PHPUnit Module is a Module for Zend Framework 2 for unit testing.

Installation
------------

 1.  Add `"prolic/humus-phpunit-module": "dev-master"` to your `composer.json`
 2.  Run `php composer.phar install`
 3.  Enable the module in your `config/application.config.php` by adding `HumusPHPUnitModule` to `modules`

Usage
-----

    ./vendor/bin/phpunit

PHPUnitListener
-------------------

If you want that on of your modules gets testet by PHPUnit, you have to implement the 
HumusPHPUnitModule\ModuleManager\Feature\PHPUnitProviderInterface in your Module.php
You can also provide more then one phpunit.xml file as array.

Sample Module:

    namespace MyModule;
    
    use HumusPHPUnitModule\ModuleManager\Feature\PHPUnitProviderInterface;
    
    class Module implements PHPUnitProviderInterface
    {
        public function getPHPUnitXmlPaths()
        {
            return array(
                dirname(dirname(__DIR__)) . '/tests/phpunit.xml'
            );
        }
    }