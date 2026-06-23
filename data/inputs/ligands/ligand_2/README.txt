# Antechamber was run with the following command:
/Users/af25016/miniforge3/envs/obss/bin/antechamber -at 2 -i antechamber.sdf -fi sdf -o antechamber.mol2 -fo mol2 -c bcc -s 2 -nc -1

# ParmChk was run with the following command:
/Users/af25016/miniforge3/envs/obss/bin/parmchk2 -s 2 -i antechamber.mol2 -f mol2 -o antechamber.frcmod

# tLEaP was run with the following command:
/Users/af25016/miniforge3/envs/obss/bin/tleap -f leap.txt
