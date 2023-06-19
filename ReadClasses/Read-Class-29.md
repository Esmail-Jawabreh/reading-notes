# Class-29

### Django Custom User
<br>

### Django Custum User Model

#### In Django, you can create a custom user model by subclassing the AbstractUser or AbstractBaseUser classes provided by Django's authentication framework. The choice between these two classes depends on your specific requirements.

#### Here's an example of creating a custom user model by subclassing AbstractUser:

- Start by creating a new Django app (if you haven't already) using the following command:

    ```
    python manage.py startapp accounts

    ```

<br>

- Open the accounts/models.py file and define your custom user model by subclassing AbstractUser. Add any additional fields or methods you need. For example:
    ```
    from django.contrib.auth.models import AbstractUser
    from django.db import models

    class CustomUser(AbstractUser):
        # Add custom fields here
        age = models.IntegerField(null=True, blank=True)
        phone_number = models.CharField(max_length=15, null=True, blank=True)

        # Add any additional methods or properties

        def get_full_name(self):
            # Custom implementation for getting the user's full name
            full_name = f"{self.first_name} {self.last_name}"
            return full_name.strip()
    ```
    #### Note: You can add any additional fields specific to your user model.

<br>

- In your project's settings.py, update the AUTH_USER_MODEL setting to point to your custom user model:

    ```
    AUTH_USER_MODEL = 'accounts.CustomUser'
    ```

<br>

- Run migrations to create the necessary database tables for your custom user model:

    ```
    python manage.py makemigrations
    python manage.py migrate
    ```

<br>


- Now you can use the CustomUser model in your views, forms, and authentication system as you would with the default Django user model.

<br>


#### By subclassing AbstractUser, you inherit all the fields and methods from the default Django user model and can add or override any of them to suit your needs.

#### Remember to update any existing references to the user model to use CustomUser instead of the default User model provided by Django.

#### If you require more control over the authentication system and want to build a custom user model from scratch, you can subclass AbstractBaseUser. However, this approach requires implementing additional methods and fields for authentication, such as password hashing and token management.




<br>

---
<br>

### What are the key benefits of using a Django Custom User Model, and how does it differ from the default Django User Model?

#### Using a Django custom user model offers several benefits and allows you to tailor the user model to your specific requirements. Here are some key benefits:

- Flexibility: 
    ##### With a custom user model, you have the flexibility to define additional fields and methods that are specific to your application's user model. This allows you to capture and store user information that may not be available in the default user model, such as age, phone number, or any other custom attributes.

<br>

- Scalability: 
    ##### By creating a custom user model, you can design a user model that scales well with your application's growth and evolving requirements. You can add or remove fields as needed without relying on the default user model's predefined fields.

<br>

- Integration with existing database schema: 
    ##### In some cases, you may already have an existing database schema that includes a user table. Creating a custom user model allows you to integrate Django's authentication system with your existing schema seamlessly.

<br>

- Improved security: 
    ##### With a custom user model, you have control over the authentication and password storage mechanisms. You can implement custom password hashing algorithms or integrate with external authentication systems if required.

<br>

- Better separation of concerns: 
    ##### A custom user model allows you to encapsulate all user-related functionality within a single model. This helps maintain a clean and modular codebase, making it easier to manage user-related logic and interactions within your application.

<br>
<br>

#### Differences from the default Django User Model:

- Fields: 
    ##### The default Django User model comes with predefined fields such as username, email, password, first name, last name, etc. With a custom user model, you can add, modify, or remove fields as per your requirements.

- Authentication fields: 
    ##### By default, the Django User model uses the username field for authentication. With a custom user model, you can choose a different field for authentication, such as email or a custom username field.

- Database schema: 
    ##### The default Django User model defines its own database schema. When using a custom user model, you have the flexibility to design your own database schema or integrate with an existing schema.

- Relationship with other models: 
    ##### If you have models in your application that have a foreign key relationship with the user model (e.g., a user is associated with certain objects), you need to update those relationships to use the custom user model instead of the default user model.


<br>


#### Remember to carefully plan and consider the impact of switching to a custom user model, especially if you have an existing project or if you are working with third-party packages that rely on the default user model.

<br>

---
<br>

### Explain the process of creating and implementing a Custom User Model in Django, including the necessary changes to settings.py and the required model fields.

- Create a new Django app (if you haven't already) using the following command:

    ```
    python manage.py startapp accounts
    ```

<br>

- Open the accounts/models.py file and define your custom user model by subclassing AbstractUser. Add any additional fields you need. For example:

    ```
    from django.contrib.auth.models import AbstractUser
    from django.db import models

    class CustomUser(AbstractUser):
        # Add custom fields here
        age = models.IntegerField(null=True, blank=True)
        phone_number = models.CharField(max_length=15, null=True, blank=True)
    ```

    #### Note: You can add any additional fields specific to your user model.

<br>

- In your project's settings.py, update the AUTH_USER_MODEL setting to point to your custom user model:

    ```
    AUTH_USER_MODEL = 'accounts.CustomUser'
    ```

<br>

- Run migrations to create the necessary database tables for your custom user model:
    ```
    python manage.py makemigrations
    python manage.py migrate
    ```

<br>

- Update any existing references to the user model in your project to use settings.AUTH_USER_MODEL instead of the default auth.User model. For example, if you have a foreign key relationship with the user model in another model, update it like this:

    ```
    from django.conf import settings

    class SomeModel(models.Model):
        user = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
        # Rest of the model fields
    ```

<br>

- Update any references to the default user model in your project's codebase, such as views, forms, or serializers, to use your custom user model instead. Replace any occurrences of User with CustomUser or settings.AUTH_USER_MODEL.

<br>

#### That's it! You have now created and implemented a custom user model in Django. You can now use the CustomUser model in your views, forms, and authentication system as you would with the default Django user model, and access the additional fields you defined.
<br>

---
<br>

### What is DjangoX and how does it complement or extend the functionality of Django? Provide an example use case for incorporating DjangoX in a project.

#### DjangoX is a Django-based framework that aims to extend and complement the functionality of Django by providing additional features and tools to simplify and enhance the development process. It is built on top of Django and offers a set of reusable components, templates, and utilities that can be used to accelerate the development of Django projects.

#### Here are some key features and use cases for incorporating DjangoX in a project:

- Enhanced Admin Interface: 
    ##### DjangoX provides an improved admin interface with additional features and customization options. It offers a modern and user-friendly UI, advanced filters, sortable columns, bulk actions, and more. This can be particularly useful when building complex content management systems or admin-heavy applications.

- Pre-built Templates: 
    ##### DjangoX includes a collection of pre-built templates that follow modern design standards and best practices. These templates can save development time by providing a starting point for building user interfaces, such as dashboards, data visualization pages, or landing pages. They are highly customizable and can be easily integrated into Django projects.

- Authentication and User Management: 
    ##### DjangoX offers ready-to-use authentication and user management components that go beyond Django's built-in authentication system. It provides features like social authentication (e.g., login with Google or Facebook), email verification, password reset, and user profile management. This can be beneficial when developing applications that require user registration and authentication.

- Advanced Forms and Form Validation: 
    ##### DjangoX provides advanced form components and form validation features. It includes form wizards, multi-step forms, form field validation, and client-side form validation. These features can simplify the process of building complex forms and handling form validation in Django projects.

- Integration with Popular Libraries: 
    ##### DjangoX integrates with popular libraries and tools commonly used in Django projects, such as Django REST Framework, Celery, and Docker. It provides templates, utilities, and examples that demonstrate how to integrate these tools effectively, saving development time and effort.

<br>

#### Example Use Case:
#### Let's consider an e-commerce project where you are building a web application to sell products online. You decide to incorporate DjangoX to enhance the functionality and development process:

- DjangoX's enhanced admin interface can be used to manage products, orders, and customer data efficiently, providing a user-friendly interface for administrators.

- You can leverage DjangoX's pre-built templates to quickly create the product listing pages, product detail pages, and checkout process UI, saving development time and ensuring a consistent and modern design.

- The authentication and user management components of DjangoX can be used to handle user registration, login, and password reset functionalities easily. Additionally, features like social authentication can enable users to log in using their Google or Facebook accounts.

- DjangoX's advanced form components and form validation features can simplify the process of building the checkout form, handling input validation, and implementing multi-step form flows.

- The integration with Django REST Framework provided by DjangoX can help you build a robust API for your e-commerce application, allowing easy integration with frontend frameworks or mobile apps.


<br>

#### In this use case, DjangoX extends Django's functionality by providing additional features, tools, and templates that specifically cater to the needs of e-commerce projects. It helps accelerate development, improves user experience, and simplifies the implementation of common features.


<br>

---
<br>

**- Esmail Jawabreh**