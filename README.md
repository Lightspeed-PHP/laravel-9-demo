# Lightspeed PHPUnit 9 Demo

This repo contains a demo of [Lightspeed](https://lightspeedphp.com) running a PHPUnit 9 testsuite.

## About

This is a new Laravel 9 app with PHPUnit 9. It runs on PHP 8.2.

There are 502 test files containing a total of 1002 individual tests. These tests have a random sleep time to simulate more realistic testing conditions that might interact with database or third-party APIs or anything else that adds time to test suites. You can see the tests in [tests/Feature](https://github.com/lightspeed-php/phpunit-9-demo/tree/main/tests/Feature).

## How It Works

The test suite is executed with the `vendor/bin/lightspeed` command. This command wraps up PHPUnit and divides up the tests based on how many test nodes are used to run the suite.

The purpose of this design is to execute the test suite in the shortest possible time. It does this by splitting the whole test suite over multiple instances that run a subset of tests in parallel, ensuring no tests are missed.

The free version of Lightspeed splits the test in a deterministic and static way across all the available nodes.  
We are working on a premium version that tracks the historic runtime of your tests and splits tests dynamically so that the entire test suite is run in the shortest time possible. For more information and to register your interest in the premium version, please email support@lightspeedphp.com

## How Does this differ to [ParaTest](https://github.com/paratestphp/paratest)?

Lightspeed is similar to ParaTest in that it runs tests in parallel. Where it differs is that ParaTest executes all the tests on the same machine whereas Lightspeed runs them on separate machines.

ParaTest will use every CPU core available to run the tests as fast as possible in one place.  
In contrast, Lightspeed can make use of many _much_ smaller machines to run tests as fast as possible.
