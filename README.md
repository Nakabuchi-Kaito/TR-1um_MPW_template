# TR-1um_MPW_template

- [Read the documentation for project](docs/info.md)

# TR-1um_MPW Precheck

Precheck for OpenSUSI MPW runs using the TR-1um Drawing Layer PDK

The precheck performs the following checks:

- Ensures there is only one top-level cell and it matches the `--top` argument.
- Checks that the origin is at (0,0), the minimum grid is 0.05um, 
- Checks the non-diagnal shape 
- Runs KLayout DRC and antenna check.

## Prerequisites

Clone the PDK with: `make clone-pdk`.

## Run the Precheck

Enable a shell with all tools: `nix-shell`

Export the environment variables:

```
export PDK_ROOT=gf180mcu && export PDK=gf180mcuD
```

Now run the precheck with your layout:

```
python3 precheck.py --input chip_top.gds
```

> [!NOTE]
> If your top-level cell name does not match the file name, you need to specify it using the `--top` argument:
>
> ```
> python3 precheck.py --input chip_top.gds --top my_top_cell
> ```
>
> If you use a slot size other than 1x1, you need to specify it using the `--slot` argument:
>
> ```
> python3 precheck.py --input chip_top.gds --slot 0p5x0p5
> ```
>
> The valid slot sizes are: `1x1`, `0p5x1`, `1x0p5`, `0p5x0p5`.