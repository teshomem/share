# share
To reproduce what i have done:
cd share/BiasAway 

$> rm -rf bgdir/ &&  python BiasAway.py g -r bgdir/  -f input/T6_SP_UP.fa -b input/Ssal.allpromoter.masked.fasta -n 52260 > stdout_bg.fa 2>log.txt

$>  grep ">"  output/bg.fa |wc -l # 48987

$>  sum=0;for count in `seq 1 100`; do tot=$(grep ">" bgdir/bg_bin_$count.txt |wc -l); sum=$(expr $sum + $tot);done;echo $sum #50676
