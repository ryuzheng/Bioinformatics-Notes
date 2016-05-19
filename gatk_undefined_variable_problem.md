# GATK undefined variable problem

使用GATK进行hard filter时发现日志出现：

```
INFO  09:05:15,295 ProgressMeter -                 | processed |    time |    per 1M |           |   total | remaining 
INFO  09:05:15,296 ProgressMeter -        Location |     sites | elapsed |     sites | completed | runtime |   runtime 
WARN  09:05:15,579 Interpreter - ![38,47]: 'QD < 2.0 || FS > 60.0 || MQ < 40.0 || MQRankSum < -12.5 || ReadPosRankSum < -8.0;' undefined variable MQRankSum 
WARN  09:05:15,591 Interpreter - ![38,47]: 'QD < 2.0 || FS > 60.0 || MQ < 40.0 || MQRankSum < -12.5 || ReadPosRankSum < -8.0;' undefined variable MQRankSum 
WARN  09:05:15,633 Interpreter - ![38,47]: 'QD < 2.0 || FS > 60.0 || MQ < 40.0 || MQRankSum < -12.5 || ReadPosRankSum < -8.0;' undefined variable MQRankSum 
INFO  09:05:16,526 ProgressMeter -            done       137.0     1.0 s       2.5 h       95.3%     1.0 s       0.0 s 
INFO  09:05:16,526 ProgressMeter - Total runtime 1.23 secs, 0.02 min, 0.00 hours 
```

或者

```
INFO  09:05:38,363 ProgressMeter -                 | processed |    time |    per 1M |           |   total | remaining 
INFO  09:05:38,363 ProgressMeter -        Location |     sites | elapsed |     sites | completed | runtime |   runtime 
WARN  09:05:38,841 Interpreter - ![26,40]: 'QD < 2.0 || FS > 200.0 || ReadPosRankSum < -20.0;' undefined variable ReadPosRankSum 
WARN  09:05:38,843 Interpreter - ![26,40]: 'QD < 2.0 || FS > 200.0 || ReadPosRankSum < -20.0;' undefined variable ReadPosRankSum 
WARN  09:05:38,856 Interpreter - ![26,40]: 'QD < 2.0 || FS > 200.0 || ReadPosRankSum < -20.0;' undefined variable ReadPosRankSum 
WARN  09:05:38,857 Interpreter - ![26,40]: 'QD < 2.0 || FS > 200.0 || ReadPosRankSum < -20.0;' undefined variable ReadPosRankSum 
WARN  09:05:38,858 Interpreter - ![26,40]: 'QD < 2.0 || FS > 200.0 || ReadPosRankSum < -20.0;' undefined variable ReadPosRankSum 
WARN  09:05:38,858 Interpreter - ![26,40]: 'QD < 2.0 || FS > 200.0 || ReadPosRankSum < -20.0;' undefined variable ReadPosRankSum 
INFO  09:05:38,904 ProgressMeter -            done        43.0     0.0 s       3.5 h       82.1%     0.0 s       0.0 s 
INFO  09:05:38,904 ProgressMeter - Total runtime 0.54 secs, 0.01 min, 0.00 hours 
```

出现`undefined variable MQRankSum`与`undefined variable ReadPosRankSum`的`WARN`警告，后经Google发现

##reference：
- [GATK undefined variable problem](http://seqanswers.com/forums/showthread.php?t=16556)