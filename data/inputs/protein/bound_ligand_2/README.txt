# gmx editconf was run with the following command:
/usr/local/gromacs/bin/gmx editconf -f input.gro -bt triclinic -box 18.215100 18.215100 18.215100 -angles 90.000000 90.000000 90.000000 -noc -noprinc -o box.gro

# gmx solvate was run with the following command:
/usr/local/gromacs/bin/gmx solvate -cs spc216 -cp box.gro -o output.gro

# gmx grompp was run with the following command:
/usr/local/gromacs/bin/gmx grompp -f ions.mdp -po ions.out.mdp -c solvated.gro -p solvated.top -o ions.tpr

# gmx genion was run with the following command:
/usr/local/gromacs/bin/gmx genion -s ions.tpr -o solvated_ions.gro -p solvated.top -neutral -conc 0.150000
