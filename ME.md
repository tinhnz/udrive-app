# Notes

- Doing: Saving `path` field of file 2:07
- Doing: Open folder 2:26
- Doing: Folder ancestors 2:37

## Works in progress

### Init project

```bash
curl -s https://laravel.build/udrive-app | bash
```

At first, it needs to download a lot of libraries and packages. It took me a while due to my slow internet connection.

### Run project

Start all containers.

```bash
./vendor/bin/sail up -d
```

Go inside main container, so that you can run all php commands.

```bash
./vendor/bin/sail bash
```

Inside the container, install dependencies and start the project

```bash
npm install
npm run dev
```

### Install lavarel/breeze

```bash
composer require lavarel/breeze --dev
php artisan breeze:install
```

### If you get errors when opening website

Add server information into vite.config.js

```js
export default defineConfig({
    server: {
        hmr: {
            host: 'localhost'
        }
    },
    // More config.
});
```

### Run migration

```bash
php artisan migrate
```

## [Optional] Email verification

- In User.php file, implements MustVerifyEmail.
- Try to register new email account, then go to localhost:8025 to get verification code.

## Make DB models (User model is already available)

php artisan make:model File -m
php artisan make:model FileShare -m
php artisan make:model StarredFile -m

- Update migration code of each models (rewatch!)
- Install laravel nested sets: lazychaser github free

```bash
composer require kalnoy/nestedset
php artisan migrate
```

!!! Learn Inertiajs/javascript?vue?
!!! Learn Nested Set Model!!!
!!! Learn Headless UI

## Build AuthenticatedLayout from scratch by reusing old code.

npm install @headlessui/vue@^1.7 // For UI components
npm install @heroicons/vue // For icons
