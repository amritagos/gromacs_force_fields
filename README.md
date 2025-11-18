# Force fields 

These force-field files are meant to be used with `gmx pdb2gmx` etc (I've been using the 2025.3-conda_forge version). 
The water files can be used in the `gmx solvate` commands.

However, I highly recommend setting the path for GMXLIB, like so: 

```bash
export GMXLIB=/path/to/library-folders
```

For instance, one could point to the top-level directory to use these force-fields. 

Note, however, that if you run the following command

```bash
gmx solvate -cp unsolvated.gro -cs tip4p.g96 -o solvate.gro -p topol.top
```
where `unsolvated.gro` is the input gro file to which water molecules will be added, only the current directory and the GMXLIB path 
will be searched for `tip4p.g96`, *even if* you provide the full path of `tip4p.g96`!
In order to get around this, I keep the water box files inside the directory pointed to by the GMXLIB path.