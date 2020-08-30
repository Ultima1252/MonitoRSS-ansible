# MonitoRSS-ansible
Ansible playbook for MonitoRSS

Only currently support Debian and only tested on buster.

Edit vars in monitorss.yml, I suggest adding the secret ones to a vault file.

playbook can be tested locally using ```vagrant up```

Ansible playbook options:
| Variable	| Description	| Default	| Type	|
| :---		| :---		| :---		| :---	|
| MONITORSS_USER | User to run MonitoRSS under | monitorss | String |
| MONITORSS_DIR | Directory to clone MonitoRSS | /opt/MonitoRSS | String |
| MONITORSS_BOT_ENABLE | Enable MonitoRSS bot | true | Bool |
| MONITORSS_WEB_ENABLE | Enable MonitoRSS web | true | Bool |

MonitoRSS bot options defined in ansible:
| Variable	| Default	| Type	|
| :---		| :---		| :---	|
| MONITORSS_BOT_LOG_LEVEL | "info" | String |
| MONITORSS_BOT_LOG_DESTINATION | "" | String |
| MONITORSS_BOT_LOG_LINKERRS | true | Bool |
| MONITORSS_BOT_LOG_UNFILTERED | true | Bool |
| MONITORSS_BOT_LOG_RATELIMITHITS | true | Bool |
| MONITORSS_BOT_LOG_FAILEDFEEDS | true | Bool |
| MONITORSS_BOT_BOT_TOKEN | "" | String |
| MONITORSS_BOT_BOT_LOCALE | "en-US" | String |
| MONITORSS_BOT_BOT_ENABLECOMMANDS | true | Bool |
| MONITORSS_BOT_BOT_PREFIX | "rss." | String |
| MONITORSS_BOT_BOT_STATUS | "online" | String |
| MONITORSS_BOT_BOT_ACTIVITYTYPE | "" | String |
| MONITORSS_BOT_BOT_ACTIVITYNAME | "" | String |
| MONITORSS_BOT_BOT_STREAMACTIVITYURL | "" | String |
| MONITORSS_BOT_BOT_OWNERIDS | '[]' | String (Single quote) |
| MONITORSS_BOT_BOT_MENUCOLOR | 5285609 | Int |
| MONITORSS_BOT_BOT_DELETEMENUS | true | Bool |
| MONITORSS_BOT_BOT_RUNSCHEEDULESONSTART | true | Bool |
| MONITORSS_BOT_BOT_EXITONSOCKETISSUES | true | Bool |
| MONITORSS_BOT_BOT_EXITONDATABASEDISCONNECT | false | Bool |
| MONITORSS_BOT_BOT_USERAGENT | 'Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:78.0) Gecko/20100101 Firefox/78.0' | String (Single Quote) |
| MONITORSS_BOT_DATABASE_URI | "mongodb://localhost:27017/rss" | String |
| MONITORSS_BOT_DATABASE_REDIS | "" | String |
| MONITORSS_BOT_DATABASE_CONNECTION | '{}' | String (Single quote) |
| MONITORSS_BOT_DATABASE_ACTICLESEXPIRE | 14 | Int |
| MONITORSS_BOT_DATABASE_DELIVERYRECORDSEXPIRE | 2 | Int |
| MONITORSS_BOT_FEEDS_REFRESHRATEMINUTES | 10 | Int |
| MONITORSS_BOT_FEEDS_ACTICLEDAILYCHANNELLIMIT | 0 | Int |
| MONITORSS_BOT_FEEDS_TIMEZONE | "America/New_York" | String |
| MONITORSS_BOT_FEEDS_DATEFORMAT | "ddd, D MMMM YYYY, h:mm A z" | String |
| MONITORSS_BOT_FEEDS_DATELANGUAGE | "en" | String |
| MONITORSS_BOT_FEEDS_DATELANDUAGELIST | '["en"]' | String (Single quote) |
| MONITORSS_BOT_FEEDS_DATEFALLBACK | false | Bool |
| MONITORSS_BOT_FEEDS_TIMEFALLBACK | false | Bool |
| MONITORSS_BOT_FEEDS_MAX | 0 | Int |
| MONITORSS_BOT_FEEDS_HOURSUNTILFAIL | 0 | Int |
| MONITORSS_BOT_FEEDS_NOTIFYFAIL | true | Bool |
| MONITORSS_BOT_FEEDS_SENDFIRSTCYCLE | true | Bool |
| MONITORSS_BOT_FEEDS_CYCLEMAXAGE | 1 | Int |
| MONITORSS_BOT_FEEDS_DEFAULTTEXT | ':newspaper:  \|  \**{title}**\n\n{link}\n\n{subscriptions}' | String (Single quote) |
| MONITORSS_BOT_FEEDS_IMGPREVIEWS | true | Bool |
| MONITORSS_BOT_FEEDS_IMGLINKSEXISTENCE | true | Bool |
| MONITORSS_BOT_FEEDS_CHECKDATES | true | Bool |
| MONITORSS_BOT_FEEDS_FORMATTABLES | false | Bool |
| MONITORSS_BOT_FEEDS_DIRECTSUBSCRIBERS | false | Bool |
| MONITORSS_BOT_FEEDS_DECODE | '{}' | String (Single quote) |
| MONITORSS_BOT_ADVANCED_SHARDS | 2 | Int |
| MONITORSS_BOT_ADVANCED_BATCHSIZE | 400 | Int |
| MONITORSS_BOT_ADVANCED_PARALLELBATCHES | 1 | Int |
| MONITORSS_BOT_ADVANCED_PARALLELRUNS | 1 | Int |
| MONITORSS_BOT_WEBURL | "" | String |

MonitoRSS bot options defined in ansible:
| Variable	| Default	| Type	|
| :---		| :---		| :---	|
| MONITORSS_WEB_LOG_LEVEL | "info" | String |
| MONITORSS_WEB_LOG_DESTINATION | "" | String |
| MONITORSS_WEB_BOT_TOKEN | "" | String |
| MONITORSS_WEB_BOT_REDIRECTURI | "http://localhost:8081/authorize" | String |
| MONITORSS_WEB_BOT_CLIENTID | "" | String |
| MONITORSS_WEB_BOT_CLIENTSECRET | "" | String |
| MONITORSS_WEB_DATABASE_URI | "mongodb://localhost:27017/rss" | String |
| MONITORSS_WEB_DATABASE_CONNECTION | '{}' | String (Single quote) |
| MONITORSS_WEB_DATABASE_REDIS | "redis://localhost" | String |
| MONITORSS_WEB_HTTP_TRUSTPROXY | false | Bool |
| MONITORSS_WEB_HTTP_SESSIONSECRET | "Tb85O5LchMzmvPAX83v98DTq0F7lzJ1gFF4V8HTzSbIxENMU0CnFy57cEt9Tf0X0" | String |
| MONITORSS_WEB_HTTP_PORT | 8081 | Int |
| MONITORSS_WEB_HTTPS_ENABLED | false | Bool |
| MONITORSS_WEB_HTTPS_PRIVATEKEY | "" | String |
| MONITORSS_WEB_HTTPS_CERTIFICATE | "" | String |
| MONITORSS_WEB_HTTPS_CHAIN | "" | String |
| MONITORSS_WEB_HTTPS_PORT | 443 | Int |

Systemd units:

monitorss.service = bot

monitorss-web.service = web



TODO:
* Add support for more OS's
* Add better support for SSL/TLS
* Add integrated testing
