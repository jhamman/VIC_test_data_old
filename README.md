VIC Test Data
========

###Datasets
- Global 0.5 degree
- Rosemount
- Stehekin
- *Pilps?*

###Contents
Each dataset directory contains the necessary and available parameters and forcings to run VIC for selected versions of the model.  The directory structure of the test data is:

    VIC_test_data
    |---VIC version (e.g. VIC.4.1.2)
    |------test setup
    |---------parameters
    |---------forcings (or tool to download forcings)
    |---------observations (optional)
    |---------archive (optional)
    |------------plots (optional)

####File naming conventions

**Parmaeter Files:**
`{test_name}_VIC.{vic_version}_{parameter_set}{_**optional_specs}.{suffix}`.  For example:  `stehikin_VIC.4.1.2_soil_frozensoil.txt` would represent the Sthekin soil parameter file formated for VIC.4.1.2 using frozen soils.

**Forcing Files:**
`{test_name}_VIC.{vic_version}_forcings_{**gridspec}{_**optional_specs}.{suffix}`.  For example:  `Rosemount_VIC.4.1.2_forcings_45.000_-93.000.txt` would represent the forcing file for the Rosemount location formated for VIC.4.1.2.

**Keyword Options:**

- `vic_version`: {4.1.2, 4.2, 5.0.0, etc.}
- `parameter_set`: {all, soil, snowbands, vegparam, veglib}
- `suffix`: {bin, txt, nc}

