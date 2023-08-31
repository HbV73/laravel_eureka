# laravel_eureka
Eureka Clients Code

#How to use
##install
composer require "piwvh/php-eureka"

##make provider
php artisan make:provider EurekaProvider

##copy below code
    /**
     * Register services.
     */
    public function register(): void
    {
        $client = new EurekaClient([
            'eurekaDefaultUrl' => 'http://localhost:8761/eureka',
            'hostName' => 'warehouse-service',
            'appName' => 'WarehouseService',
            'ip' => '127.0.0.1',
            'port' => ['8006', true],
            'homePageUrl' => 'http://localhost:8006',
            'statusPageUrl' => 'http://localhost:8006/info',
            'healthCheckUrl' => 'http://localhost:8006/health',
            'discoveryStrategy' => ''
        ]);
        $client->register();
    }
