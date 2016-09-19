### Grepping for slow SQL

```grep -P '\((?<!\d)\d{3,4}\.\dms(?!\d)\)' log/production.log ```

Matches something like the following:

```
D, [2016-09-19T12:45:00.498464 #1415] DEBUG -- :   HiveQueue Load (235.1ms)  SELECT `hive_queues`.* FROM `hive_queues`  WHERE `hive_queues`.`id` IN (16, 63, 64, 267, 279)
D, [2016-09-19T12:36:55.879000 #1415] DEBUG -- :   Batch Load (1192.2ms)  SELECT `batches`.* FROM `batches`  WHERE `batches`.`project_id` IN (1, 4, 9, 10, 12, 14, 15, 16, 17, 18, 21, 22, 23, 24, 26, 28, 31, 32, 33, 34, 35, 36, 38, 39, 40, 41, 42, 43, 44, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 76, 77, 78, 79, 80, 82, 83, 85, 86, 87, 88, 89, 90, 91, 92, 93, 95, 96, 97, 98, 99, 100, 101, 102, 103, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131)  ORDER BY `batches`.`id` DESC
```

