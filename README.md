# TR-1um_MPW_template

- [Read the documentation for project](docs/info.md)

# TR-1um_MPW actions

GitHub CI/CD actions will perform below.

The **precheck** performs the following checks:

- TOP cell name is match to info.yaml
- TOP cell is not prural.
- TOP cell drawing area matched into (-1250,-1250):(1250,1250).
- TOP cell include OpenSUSI recommeded Frame cell ['OSS_FRAME', 'OSS_FRAME_TEG']

The **drc** performs the following checks:
- Runs KLayout DRC(Drawing) and antenna check.

