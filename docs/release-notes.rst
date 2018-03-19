.. ===============LICENSE_START=======================================================
.. Acumos CC-BY-4.0
.. ===================================================================================
.. Copyright (C) 2017-2018 AT&T Intellectual Property & Tech Mahindra. All rights reserved.
.. ===================================================================================
.. This Acumos documentation file is distributed by AT&T and Tech Mahindra
.. under the Creative Commons Attribution 4.0 International License (the "License");
.. you may not use this file except in compliance with the License.
.. You may obtain a copy of the License at
..
.. http://creativecommons.org/licenses/by/4.0
..
.. This file is distributed on an "AS IS" BASIS,
.. WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
.. See the License for the specific language governing permissions and
.. limitations under the License.
.. ===============LICENSE_END=========================================================

=============
Release Notes
=============

Version 0.5.0
=============
- The runtime field is now a list instead of an object, allowing for multiple runtimes to be specified. For example, to allow R + Java (e.g. to use RWeka) or R + Python (e.g to use kerasR).

Example:

.. code:: JSON

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


Version 0.4.0
=============

- Introduced arbitrary function names, removing reserved functions such as fit, predict, etc.
- Descriptions added to clarify the purpose of various schema fields.
- Added regex pattern to required schema field.

Example:

.. code-block:: JSON

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


Versions 0.1.0 - 0.3.0
======================

- Older schemas used during initial development.
- Now deprecated and should not be used.