# Behavioral Interview: Leadership Principles

LP="Customer Obsession:Ownership:Invent and Simplify:Are Right, A Lot:Learn and Be Curious:Hire and Develop the Best:Insist on the Highest Standards:Think Big:Bias for Action:Frugality:Earn Trust:Dive Deep:Have Backbone; Disagree and Commit:Deliver Results"
IFS=:
for i in $LP; do
  echo $i
  n=${#i}
  printf "%0.s-" {1..$n}
  echo ""
done


## Tags
