## sb-mirror
Create an rsync mirror of the SponsorBlock database

Data and mirror contents are licenced and used under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) from https://sponsor.ajay.app/.

Environment Variables
```conf
SQLITE=TRUE # set to auto-generate sqlite .db file to /export  
MIRROR_URL=qc.mchang.xyz # override to set upstream mirror, must be rsync  
MIRROR=TRUE # set to start rsyncd and cron to run every 5 minutes
```

## sb-server-runner
Downloads and runs [SponsorBlockServer](https://github.com/ajayyy/SponsorBlockServer) from the master branch

SponsorBlockServer is licenced under the [MIT Licence](https://github.com/ajayyy/SponsorBlockServer/blob/master/LICENSE)

Environment Variables
```conf
DBINIT=TRUE # set to only initialize the database and immediately exit
```

## rsync
Just a container with rsyncd

## docker-compose.yml
Postgres Setup
1. Download the mirror to a known directory
2. Set `postgresExportPath` to the mirror directory

SQLite Setup
1. Set `SQLITE=TRUE` on sb-mirror
2. Set the export directories for `SponsorBlockDB.db`

Uncomment the respective config file mapping

Database Comparison
| Database 	| Postgres 	| SQLite 	| MSSQL 	|
|---	|---	|---	|---	|
| Advantages 	| Performs Well 	| Performs Poorly 	| - 	|
| Disadvantages 	| RAM intensive COPY on start 	| Starts Immediately 	| Not Supported 	|

The default admin ID is a hash of `WjGS5C9WRhVzjmB8KdrdR8jLqvTwC5q5kAGdC5WVzfDcbAPX`

