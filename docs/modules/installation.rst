#############
Installation
#############

How to install Jeol Api in your system

```
git clone https://github.com/stevemats/jeol.git
```

-------------
Prerequisites
-------------

* python3.6
* virtualenv
* pip
* mysql5
### Installing

To install dependecies for this project:

```bash
pip install -r requirements/<env>.txt
```

To install django-mysql-pool

```bash
pip install git+https://github.com/smartfile/django-mysqlpool.git
```

To install django-audit-log

```bash
pip install git+https://github.com/vvangelovski/django-audit-log.git
```

## Config directory

The config dir holds all configurations and settings. The `base.py` file is the main settings file with global configs. The other files are an extension of this file and are labelled as per their environment.

```bash
.
├── api_urls.py
├── settings
│   ├── base.py
│   ├── celery.py
│   ├── development.py
│   ├── export.py
│   ├── production.py
│   ├── staging.py
│   └── test.py
├── urls.py
└── wsgi.py

```

## System Directory
The VRP code layout is as described below. All the model classes should inherit the `BaseModel.py` from `core`. The core defines all structural changes that run across all apps. The helper folder contains the helper functions to support the models interaction with other models or to for integrated functionality. The analytics contain functions that are optimized at query level to provide required business data, They are the data analytics for a specific app. The templates at root level store system wide templates and changee_lists. On the other hand, the templates within the app, are specific templates run by custom views within the app.

---
.
├── apps
│   ├── app_name
│   │   ├── admin
│   │   │   ├── ModelAdminClass1Admin.py
│   │   │   ├── ModelAdminClass2Admin.py
│   │   │   └── __init__.py
│   │   ├── analytics
│   │   │   ├── analytics_group1_functions.py
│   │   │   ├── analytics_group2_functions.py
│   │   │   └── __init__.py
│   │   ├── api
│   │   │   ├── filters
│   │   │   │   ├── Model1ClassFilter.py
│   │   │   │   ├── Model2ClassFilter.py
│   │   │   │   └── __init__.py
│   │   │   ├── serializers
│   │   │   │   ├── Model1ClassSerializer.py
│   │   │   │   ├── Model2ClassSerializer.py
│   │   │   │   └── __init__.py
│   │   │   ├── views
│   │   │   │   ├── Model1ClassView.py
│   │   │   │   ├── Model2ClassView.py
│   │   │   │   └── __init__.py
│   │   │   ├── urls.py
│   │   │   └── __init__.py
│   │   ├── forms
│   │   │   ├── Model1ClassForm.py
│   │   │   │── Model2ClassForm.py
│   │   │   └── __init__.py
│   │   ├── helpers
│   │   │   ├── model_help_group1_functions.py
│   │   │   │── model_help_group2_functions.py
│   │   │   └── __init__.py
│   │   ├── migrations
│   │   │   ├── migration_file_1.py
│   │   │   ├── migration_fil_2.py
│   │   │   └── __init__.py
│   │   ├── models
│   │   │   ├── Model1.py
│   │   │   ├── Model2.py
│   │   │   └── __init__.py
│   │   ├── schema
│   │   │   ├── object_type
│   │   │   │   ├── Model1DjangoObjectType.py
│   │   │   │   ├── Model2DjangoObjectType.py
│   │   │   │   └── __init__.py
│   │   │   └── query_object
│   │   │       ├── SchemaQuery1.py
│   │   │       ├── SchemaQuery2.py
│   │   │       └── __init__.py
│   │   ├── static
│   │   │   ├── csss
│   │   │   │   ├── css_file_1.css
│   │   │   │   ├── css_file_2.css
│   │   │   │   └── __init__.py
│   │   │   └── js
│   │   │       ├── js_file_1.js
│   │   │       ├── js_file_2.js
│   │   │       └── __init__.py
│   │   ├── templates
│   │   │   ├── Model1.py
│   │   │   ├── Model2.py
│   │   │   └── __init__.py
│   │   ├── tests
│   │   │   ├── models
│   │   │   │   ├── model_1_test_1.py
│   │   │   │   ├── model_2_test_2.py
│   │   │   │   └── __init__.py
│   │   │   ├── admin
│   │   │   │   ├── admin1_test_1.py
│   │   │   │   ├── admin_2_test_2.py
│   │   │   │   └── __init__.py
│   │   │   └── views
│   │   │       ├── js_file_1.py
│   │   │       ├── js_file_2.py
│   │   │       └── __init__.py
│   │   ├── views
│   │   │   ├── view_function_1.py
│   │   │   ├── view_function_2.py
│   │   │   └── __init__.py
│   │   ├── urls.py
│   │   └── __init__.py
│   ├── schema.py
│   └── __init__.py
├── assets
│   ├── csss
│   │   ├── css_file_1.css
│   │   ├── css_file_2.css
│   │   └── __init__.py
│   ├── js
│   │   ├── js_file_1.js
│   │   ├── js_file_2.js
│   │   └── __init__.py
│   ├── img
│   │   ├── js_file_1.py
│   │   ├── js_file_2.py
│   │   └── __init__.py
│   ├── plugins
│   │   ├── plugin_1_folder
│   │   ├── plugin_2_folder
│   │   └── __init__.py
│   └── fonts
│       ├── font_file.font
│       └── __init__.py
├── config
├── core (check App)
├── deploy
├── hooks
├── log
├── media
├── requirements
├── scripts
├── static
├── tempfiles
├── templates
├── tests
├── utils (Check App)
├── vendor
├── .env
├── pytest.ini
└── manage.py
---