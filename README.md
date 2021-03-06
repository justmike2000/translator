# translator
Language Translation API

# Description
HTTP Langugage Translation API.  Currently uses redis to persist translations.

# Requirments

Python 3.7+ (https://www.python.org/downloads/)
Docker 18+ (https://docs.docker.com/engine/install/ubuntu/)

# Building

## Build Dev

Build pip dependencies dev

```
make build-dev
```

## Build Production

Build pip dependencies production

```
make build
```

# Running

## Running Development Mode

```
make run HOST=<host ip or 0.0.0.0>
```

## Running Production Deployment

```
<Todo>
```

# Routes

Index Status

```
/
```

yields information regarding service such as version and langugages

```
{"service": "translate", "supported_langugages": ["english", "spanish"], "version": "0.0.1"}
```

---

* Translate a word (**HTTP GET REQUEST**):

```
/translate/<from langugage>/<to language>/<word to translate>/
```

for example:
```
/translate/english/spanish/library/
```

yields if the translation exists:
```
{"translation": "bibliotheca"}
```

otherwise if no translation exists you will receive a 404

---

* Add new translation (**HTTP POST REQUEST**):
```
/translate/<from langugage>/<to language>/<word to translate>/<translation>/

```

---

* Delete translation (**HTTP DELETE REQUEST**):
```
/translate/<from langugage>/<to language>/<word to translate>/

```

# Error conditions

In cases of error you will recieve a payload with an error key and value explaining the error:

```
/translate/english/spanish/.....
```

yields

```
{"error": "invalid input"}
```

# Tests

To run unit tests:

```
make test
```

# Currently Supported langugages

```
Spanish
English
```
