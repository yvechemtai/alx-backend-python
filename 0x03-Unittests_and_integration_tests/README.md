# README.md

## 0x03. Unittests and Integration Tests

### Introduction

This project focuses on implementing unit tests and integration tests for various functions and classes using the `unittest` framework in Python. The primary goal is to ensure the correctness and reliability of the codebase, covering both standard inputs and corner cases.

### Table of Contents

1. [UnitTests and Integration Tests](#unittests-and-integration-tests)
2. [Learning Objectives](#learning-objectives)
3. [Requirements](#requirements)
4. [File Structure](#file-structure)
5. [Tasks](#tasks)
   - [Task 0: Parameterize a unit test](#task-0-parameterize-a-unit-test)
   - [Task 1: Parameterize a unit test exception](#task-1-parameterize-a-unit-test-exception)
   - [Task 2: Mock HTTP calls](#task-2-mock-http-calls)
   - [Task 3: Parameterize and patch](#task-3-parameterize-and-patch)
   - [Task 4: Parameterize and patch as decorators](#task-4-parameterize-and-patch-as-decorators)
   - [Task 5: Mocking a property](#task-5-mocking-a-property)
   - [Task 6: More patching](#task-6-more-patching)
   - [Task 7: Parameterize](#task-7-parameterize)
   - [Task 8: Integration test - fixtures](#task-8-integration-test-fixtures)
   - [Task 9: Integration tests](#task-9-integration-tests)

### UnitTests and Integration Tests

#### Unit Tests

Unit testing is the process of testing individual functions to ensure they return expected results for various inputs. For this project, we use the `unittest` framework to create test cases for the `utils` module.

#### Integration Tests

Integration tests focus on testing code paths end-to-end, particularly interactions between different parts of the code. These tests cover functions that make external calls such as HTTP requests, file I/O, and database I/O.

### Learning Objectives

Upon completion of this project, you should be able to:

- Differentiate between unit and integration tests.
- Apply common testing patterns such as mocking, parametrizations, and fixtures.
- Understand and implement memoization in testing scenarios.

### Requirements

- All code should be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- Follow PEP 8 style guidelines using `pycodestyle` version 2.5.
- Documentation is mandatory for all modules, classes, and functions.
- Use type annotations for functions and coroutines.

### File Structure

```
0x03-Unittests_and_integration_tests/
|-- test_utils.py
|-- test_client.py
|-- utils.py
|-- client.py
|-- fixtures.py
|-- README.md
```

### Tasks

#### Task 0: Parameterize a unit test

Familiarize yourself with the `utils.access_nested_map` function and understand its purpose. Create a `TestAccessNestedMap` class that inherits from `unittest.TestCase`...

Implement the `TestAccessNestedMap.test_access_nested_map` method to test that the method returns what it is supposed to.

Decorate the method with `@parameterized.expand` to test the function for following inputs:

- `nested_map={"a": 1}, path=("a",)`
- `nested_map={"a": {"b": 2}}, path=("a",)`
- `nested_map={"a": {"b": 2}}, path=("a", "b")...

The body of the test method should not be longer than 2 lines.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_utils.py

#### Task 1: Parameterize a unit test exception

Implement `TestAccessNestedMap.test_access_nested_map_exception`. Use the `assertRaises` context manager to test that a `KeyError` is raised for the following inputs (use `@parameterized.expand`):

- `nested_map={}, path=("a",)`
- `nested_map={"a": 1}, path=("a", "b")...

Also make sure that the exception message is as expected.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_utils.py

#### Task 2: Mock HTTP calls

Familiarize yourself with the `utils.get_json` function.

Define the `TestGetJson(unittest.TestCase)` class and implement the `TestGetJson.test_get_json` method to test that `utils.get_json` returns the expected result...

We don’t want to make any actual external HTTP calls. Use `unittest.mock.patch` to patch `requests.get`. Make sure it returns a `Mock` object with a `json` method that returns `test_payload`...

Test that the mocked `get` method was called exactly once (per input) with `test_url` as argument.

Test that the output of `get_json` is equal to `test_payload`.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_utils.py

#### Task 3: Parameterize and patch

Read about memoization and familiarize yourself with the `utils.memoize` decorator.

Implement the `TestMemoize(unittest.TestCase)` class with a `test_memoize` method.

Inside `test_memoize`, define following class...

Use `unittest.mock.patch` to mock `a_method`. Test that when calling `a_property` twice, the correct result is returned but `a_method` is only called once using `assert_called_once`.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_utils.py

#### Task 4: Parameterize and patch as decorators

Familiarize yourself with the `client.GithubOrgClient` class.

In a new `test_client.py` file, declare the `TestGithubOrgClient(unittest.TestCase)` class and implement the `test_org` method...

This method should test that `GithubOrgClient.org` returns the correct value.

Use `@patch` as a decorator to make sure `get_json` is called once with the expected argument but make sure it is not executed...

Use `@parameterized.expand` as a decorator to parametrize the test with a couple of org examples...

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_client.py

#### Task 5: Mocking a property

`memoize` turns methods into properties. Read up on how to mock a property (see resource).

Implement the `test_public_repos_url` method to unit-test `GithubOrgClient._public_repos_url`.

Use `patch` as a context manager to patch `GithubOrgClient.org` and make it return a known payload...

Test that the result of `_public_repos_url` is the expected one based on the mocked payload.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_client.py

#### Task 6: More patching

Implement `TestGithubOrgClient.test_public_repos` to unit-test `GithubOrgClient.public_repos`.

Use `@patch` as a decorator to mock `get_json` and make it return a payload of your choice.

Use `patch` as a context manager to mock `GithubOrgClient._public_repos_url` and return a value of your choice...

Test that the list of repos is what you expect from the chosen payload.

Test that the mocked property and the mocked `get_json` was called once.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_client.py

#### Task 7: Parameterize

Implement `TestGithubOrgClient.test_has_license` to unit-test `GithubOrgClient.has_license`.

Parametrize the test with the following inputs...

You should also parameterize the expected returned value.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_client.py

#### Task 8: Integration test - fixtures

We want to test the `GithubOrgClient.public_repos` method in an integration test. That means that we will only mock code that sends external requests...

Create the `TestIntegrationGithubOrgClient(unittest.TestCase)` class and implement the `setUpClass` and `tearDownClass`...

Use `@parameterized_class` to decorate the class and parameterize it with fixtures found in `fixtures.py`...

Implement the `tearDownClass` class method to stop the patcher.

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_client.py

#### Task 9: Integration tests

Implement the `test_public_repos` method to test `GithubOrgClient.public_repos`.

Make sure that the method returns the expected results based on the fixtures.

Implement `test_public_repos_with_license` to test the `public_repos` with the argument `license="apache-2.0"` and make sure the result matches the expected value from the fixtures...

Repo:

GitHub repository: alx-backend-python
Directory: 0x03-Unittests_and_integration_tests
File: test_client.py
