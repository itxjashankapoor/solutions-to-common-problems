## How to run laravel queue worker in cpanel or shared hosting?

 1. Go to `app/Console/Kernel.php`
 2. Add following code `$schedule->command('queue:work --tries=2 --stop-when-empty')->everyMinute()->withoutOverlapping()->runInBackground();`

**if you want to check visually whether queue worker is running or not then add following code at the end of above command** 

    ->appendOutputTo( storage_path('logs/queue-logs.log') )
    ->before( function() { info("before queue worker run"); } )
    ->after( function () { info("after queue worker ran"); })
Now you can check `storage/logs/queue-logs.log` if queue worker is running or not
