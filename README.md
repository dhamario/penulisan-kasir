git clone https://github.com/dhamario/penulisan-kasir.git
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate --seed
php artisan serve
