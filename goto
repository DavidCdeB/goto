function goto() {
  A=$1
  cd `qstat -f ${A} |  sed -n -e '/Output_Path/,/Priority/ p'  | sed -e '$d' | sed 's/Output_Path = .*://' | xargs | sed -e 's/ //g' | sed 's/[^\/]*$//'`
}

