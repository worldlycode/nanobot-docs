# Tests

Last updated 4/26/2025 by Worldly Woman

The importance of writing test code on an ongoing basis is becomming apparant to me.  This is especially so with the involvement of multiple contributors.  

Obviously this test folder should only exist in the development code (as opposed to the deployed production code)

## Pytest

Currently we are using the `pytest` module for our tests.  As of the date of the writing of this post the test directory contains the following tests:

```bash
├── tests/
│   ├── test_database_retrieval.py
│   ├── test_config_settings.py
│   ├── test_transaction.py
│   ├── test_chunking_service.py
│   ├── test_error_handling.py
│   ├── test_document_service.py
│   ├── test_pydantic_validator.py
│   ├── __init__.py
```

This entire test code can be run from the root directory by running

```bash
pytest tests
```

To be rigerously honest, I asked Claude to generate most of these tests, though I have modified some of them.  But the idea is for every module that we write we should have some tests that continuously test the functionality of the module, and run this test code frequently, at least daily.  

This will let us catch quickly where our code may have inadvertly gotten broken or had undesired effects and allow us to fix things quickly.  

