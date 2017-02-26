---
id: 421
title: Get MySQL full database size
date: 2013-08-09T16:35:12+00:00
author: ereslibre
layout: post
original_url: http://blog.ereslibre.es/?p=421
dsq_thread_id:
  - "1589715842"
dsq_needs_sync:
  - "1"
categories:
  - Development
---
If you have searched on the internets how to get the full MySQL database size, you have probably read something like this:

<pre class="lang:default decode:true ">SELECT CONCAT(sum(ROUND((DATA_LENGTH + INDEX_LENGTH - DATA_FREE) / 1024 / 1024,2))," MB") AS Size FROM INFORMATION_SCHEMA.TABLES where TABLE_SCHEMA = 'database_name';</pre>

For certain DB, I was getting:

<pre class="lang:default decode:true ">ERROR 1690 (22003): BIGINT UNSIGNED value is out of range in '((`information_schema`.`TABLES`.`DATA_LENGTH` + `information_schema`.`TABLES`.`INDEX_LENGTH`) - `information_schema`.`TABLES`.`DATA_FREE`)'</pre>

So, here is your fix:

<pre class="lang:default decode:true">SELECT CONCAT(sum(ROUND((CAST(DATA_LENGTH + INDEX_LENGTH AS SIGNED) - CAST(DATA_FREE AS SIGNED)) / 1024 / 1024,2))," MB") AS Size FROM INFORMATION_SCHEMA.TABLES where TABLE_SCHEMA = 'database_name';</pre>
