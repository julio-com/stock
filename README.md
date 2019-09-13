The module updates stock in Magento 2 from Dropbox files.

## How to install
```
bin/magento maintenance:enable
rm -rf composer.lock
composer clear-cache
composer require julio.com/stock:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US es_MX
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Mgs/claue \
	-f en_US es_MX
bin/magento maintenance:disable
bin/magento cache:enable
```

## How to upgrade
```
bin/magento maintenance:enable
composer remove julio.com/stock
rm -rf composer.lock
composer clear-cache
composer require julio.com/stock:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US es_MX
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Mgs/claue \
	-f en_US es_MX
bin/magento maintenance:disable
bin/magento cache:enable
```

If you have problems with these commands, please check the [detailed instruction](https://mage2.pro/t/263).