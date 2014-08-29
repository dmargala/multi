multi
======

Provides a uniform interface across different computing environments for running multiple jobs . 

Basic usage examples: 

```
multi --queue --split 0:10:1 --run "echo Job NNN > NNN.log"
multi --nohup --split 0:10:1 --run "echo Job NNN > NNN.log"
multi --qsub --split 0:10:1 --run "echo Job NNN"
```

More detailed examples:

Manage 20 jobs, using 4 processes at a time: 
```
multi --queue --n-parallel 4 --split 0:200:10 --run "./g3cosmos.py --verbose --nobs 10 --first-obs NNN --input cosmos.json --save cosmos > cosmos.NNN.log"
```

Launch 20 jobs to run in background via nohup:
```
multi --nohup --split 0:200:10 --run "./g3cosmos.py --verbose --nobs 10 --first-obs NNN --input cosmos.json --save cosmos > cosmos.NNN.log"
```

Launch 20 jobs via qsub:
```
multi --qsub --N cosmos --q dm --output log --split 0:200:10 --run "./g3cosmos.py --verbose --nobs 10 --first-obs NNN --input cosmos.json --save cosmos"
```

Install by copying into /usr/local/bin or somewhere similar.
