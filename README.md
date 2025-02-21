## 🚀 Quick Start

1. Composer install

    ```php
    composer install
    ```

2. Npm Install

    ```php
    npm install
    ```

3. Copy .env

    ```php
    cp .env.example .env
    ```

4. Configure your database in .env

    ```php
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=langkahpemula
    DB_USERNAME=root
    DB_PASSWORD=
    ```

5. Configure your google sign in cliend id and secret (optional)

    ```php
    #google auth
    GOOGLE_CLIENT_ID=
    GOOGLE_CLIENT_SECRET=
    GOOGLE_REDIRECT_URI=http://localhost:8000/admin/oauth/callback/google
    ```

6. Configure your resend for email sending (optional)

    ```php
    #resend
    MAIL_MAILER=resend
    MAIL_HOST=127.0.0.1
    MAIL_PORT=2525
    MAIL_USERNAME=null
    MAIL_PASSWORD=null
    MAIL_ENCRYPTION=null
    RESEND_API_KEY=
    MAIL_FROM_ADDRESS="admin@domain.com"
    MAIL_FROM_NAME="${APP_NAME}"
    ```

7. Migrate your database

    ```php
    php artisan migrate:fresh --seed
    ```

8. Artisan Serve

    ```php
    php artisan serve
    ```

9. Npm run dev

    ```php
    npm run dev
    ```

10. If run successfully you will get this login interface

    ![image.png](.github/images/login-screen.png)

11. When signed in it will show this (not much yet but it getting there :) )

    ![image.png](.github/images/after-login-without-rbac.png)

12. Next step is to setup the RBAC, first generate the role and permission

    ```php
    php artisan shield:generate --all
    ```

13. It will ask which panel do you want to generate permission/policies for choose the admin panel.
14. Setup the super admin using this command

    ```php
    php artisan shield:super-admin
    ```

    ![image.png](.github/images/provide-superadmin.png)

15. Choose your super admin user and login again.

    ![image.png](.github/images/after-login-rbac.png)

## Security

Set your app Debug to false in .env file

```php
APP_NAME="Langkah_Pemula"
APP_ENV=local
APP_KEY=base64:gWUd7RPrCZm6iu7qFddY3039BQLroNHJ0nqKcBr8eeA=
APP_DEBUG=false
APP_TIMEZONE=UTC
APP_URL=https://localhost:8000
```

## main.yml

```
    git pull
    composer install
    php artisan migrate:fresh --seed
    php artisan shield:generate --all
    php artisan db:seed --class=ShieldSeeder
    php artisan shield:super-admin --user=11
    php artisan filament:optimize
```
