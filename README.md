# graphQl-with-Django
Implement of graphQl with Django frame work.

## Requirements

Python 3.9.11

----------------
## Installation
  * ### Install Django:
    sudo apt install python3-django
  * ### Install with pip in a Virtual Environment
    sudo apt install python3-pip python3-venv
  * ### Create a virtual environment with venv
    python3 -m venv my_env
  * ### Activate virtual environment
    source my_env/bin/activate
  * ### Install mysql in our project
    **1)** sudo apt-get install python3-dev default-libmysqlclient-devbuild-essential
    **2)** pip install mysqlclient
  * ### Integrating GraphQL into our project
    pip install graphene-django

      * It will giving some error with installing.
        ### linux:
          path: ```YOUR_VENV/lib/PYTHON_VERSION/site-packages/graphene_django/utils/utils.py```

        ### windows:
          path: ```YOUR_VENV/lib/site-packages/graphene_django/utils/utils.py```

        ### Replace follwing lines of code.

          from django.utils.encoding import force_text
            **to**
          from django.utils.encoding import force_str
              **And**
          def _camelize_django_str(s):
            if isinstance(s, Promise):
                s = force_text(s)
            return to_camel_case(s) if isinstance(s, six.string_types) else s
            **to**
          def _camelize_django_str(s):
            if isinstance(s, Promise):
                s = force_str(s)
            return to_camel_case(s) if isinstance(s, six.string_types) else s
------
## Run the project:
  **1)** python manage.py makemigrations
  **2)** python manage.py migrate
  **3)** python manage.py createsuperuser
  **4)** python manage.py runserver

  * #### Open Admin url:
    http://127.0.0.1:8000/admin/
  * #### Open GraphQl url:
    http://127.0.0.1:8000/graphql
