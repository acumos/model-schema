# Release Notes

## 0.5.0
* The runtime field is now a list instead of an object, allowing for multiple runtimes to be specified.
  * For example, to allow R + Java (e.g. to use RWeka) or R + Python (e.g to use kerasR).

Example:

```javascript
{
  "schema": "acumos.schema.model:0.5.0",
  "name": "my-model",
  "runtime": [
    {
      "name": "python",
      "version": "3.4.5",
      "dependencies": {
        "pip": {
          "indexes": [],
          "requirements": [
            {
              "name": "scikit-learn",
              "version": "0.18.0"
            }
          ]
        },
        "conda": {
          "channels": [],
          "requirements": []
        }
      }
    }
  ],
  "methods": {
    "transform": {
      "input": "DataFrame",
      "output": "Classification",
      "description": "Classifies the input iris data as one of 3 possible classes "
    }
  }
}
```

## 0.4.0
* Introduced arbitrary function names, removing reserved functions such as fit, predict, etc.
* Descriptions added to clarify the purpose of various schema fields.
* Added regex pattern to required schema field.

Example:

```javascript
{
  "schema": "acumos.schema.model:0.4.0",
  "name": "my-model",
  "runtime": {
    "name": "python",
    "version": "3.4.5",
    "dependencies": {
      "pip": {
        "indexes": [],
        "requirements": [
          {
            "name": "scikit-learn",
            "version": "0.18.0"
          }
        ]
      },
      "conda": {
        "channels": [],
        "requirements": []
      }
    }
  },
  "methods": {
    "transform": {
      "input": "DataFrame",
      "output": "Classification",
      "description": "Classifies the input iris data as one of 3 possible classes "
    }
  }
}
```

## 0.1.0 - 0.3.0
* Older schemas used during initial development.
* Now deprecated and should not be used.