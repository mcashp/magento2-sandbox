Welcome to the MCASHP Magento 2 sandbox
=======================================

The sandbox gets you started with the MCASHP Magento 2 modules and optional the Magento 2 sample data.

## Included Magento2 modules
#### [MCASHP Core](https://github.com/mcashp/magento2-module-affiliate)
Configuration admin for common MCASHP settings
#### [MCASHP Affiliate](https://github.com/mcashp/magento2-module-core)
Let webmaster and influencer advertise your products for a given commission in %.
The payouts are automatically handled by the [MCASHP affiliate and marketing platform](https://www.mcashp.com/register/850).
It's possible to run your own instance of MCASHP as whitelabel.
For more information contact us by mail (hilfe@mcashp.com) or via user support form at [https://www.mcashp.com/](https://www.mcashp.com/register/850).

## Requirements
[MCASHP webmaster account](https://www.mcashp.com/register/850)
[Magento system requirements](http://devdocs.magento.com/magento-system-requirements.html)
[Magento connect authentication keys](http://devdocs.magento.com/guides/v2.0/install-gde/prereq/connect-auth.html) (only when you want to sample data)

## Install sandbox

#### Clone repository and install dependencies

    git clone ssh://git@github.com:mcashp/magento2-sandbox.git mcashp-magento2-sandbox
    cd mcashp-magento2-sandbox
    composer install --prefer-dist

#### Setup instance

Setup via web interface `http://mcashp-magento2-sandbox.dev/setup` or by the following CLI command:

    php bin/magento setup:install \
        --db-host=127.0.0.1 \
        --db-name=mcashp_magento2_sandbox \
        --db-user=mcashp_magento2_sandbox \
        --db-password=tops3cr3t \
        --backend-frontname=admin \
        --base-url=http://mcashp-magento2-sandbox.dev/ \
        --language=en_US \
        --timezone=UTC \
        --currency=EUR \
        --admin-lastname=Admin \
        --admin-firstname=Admin \
        --admin-email=info@example.com \
        --admin-user=admin \
        --admin-password=tops3cr3t \
        --use-rewrites=1 \
        --session-save=db \
        --cleanup-database

#### Sample data (optional)

You may need to enter your [Magento connect authentication keys](http://devdocs.magento.com/guides/v2.0/install-gde/prereq/connect-auth.html) at these step.

    php bin/magento sampledata:deploy
    php -dmemory_limit=300M bin/magento setup:upgrade

#### Finalize installation

    php -dmemory_limit=300M bin/magento setup:di:compile
    php bin/magento setup:static-content:deploy

## Configuration

Login as admin `http://mcashp-magento2-sandbox.dev/admin`

#### Configure MCASHP modules

	Stores -> Configuration -> MCASHP

## Play in the sandbox

Have fun. Your feedback is welcome!

    http://mcashp-magento2-sandbox.dev/
