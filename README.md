# eroomservice

To clone this repo you will need to create the following files:

app/etc/config.php
app/etc/env.php
.htaccess

These are available on dev site.

Database Setup:
MySQL Dump is included eroom_m2db.sql this is updated from each commit from dev site.

<h2>Step 1: Verify your prerequisites</h2>

Use the following table to verify you have the correct prerequisites to install the Magento software.

<table>
	<tbody>
		<tr>
			<th>Prerequisite</th>
			<th>How to check</th>
			<th>For more information</th>
		</tr>
	<tr>
		<td>Apache 2.2 or 2.4</td>
		<td>Ubuntu: <code>apache2 -v</code><br>
		CentOS: <code>httpd -v</code></td>
		<td><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/apache.html">Apache</a></td>
	</tr>
	<tr>
		<td>PHP 5.6.x, 7.0.2 or 7.0.6</td>
		<td><code>php -v</code></td>
		<td><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/php-ubuntu.html">PHP Ubuntu</a><br><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/php-centos.html">PHP CentOS</a></td>
	</tr>
	<tr><td>MySQL 5.6.x</td>
	<td><code>mysql -u [root user name] -p</code></td>
	<td><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/mysql.html">MySQL</a></td>
	</tr>
</tbody>
</table>

<h2>Step 2: Prepare to install</h2>

After verifying your prerequisites, perform the following tasks in order to prepare to install the Magento software.

1.	Create Database, Username and Password. Import sql dump included in repo.
2.	Clone repository and setup app/etc/config.php and app/etc/env.php. Dev files can be used just ftp into and grab files.


<h3>Core Modification</h3>
1. vendor/magento/module-eav/Model/ResourceModel/Entity/Attribute.php
	477 - $is_category = empty($option['is_category'][$optionId]) ? 0 : $option['is_category'][$optionId];
	478 - $option_price = empty($option['option_price'][$optionId]) ? 0 : $option['option_price'][$optionId];
	482 - 'is_category' => $is_category, 'option_price' => $option_price
	
2. vendor/magento/framework/Search/Adapter/Mysql/Adapter.php
	

3. vendor/magento/framework/View/Page/Config.php
4. vendor/magento/framework/View/Page/Title.php
5. vendor/magento/module-catalog/Helper/Image.php
	change SCOPE_STORE to SCOPE_WEBSITES
	


	
<h3>Extension Modification</h3>	
1. app/code/Amasty/Shopby/Model/ResourceModel/Fulltext/Collection.php
	294 to 300
	
<h3>Email Logo Directory</h3>	
1. /vendor/magento/module-email/Model/AbstractTemplate.php
	392 to 393


