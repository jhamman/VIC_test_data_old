*** VIC SAMPLE DATASET - STEHEKIN RIVER BASIN ***

Contents:
  forcing/      : VIC daily meteorological forcing files (binary)
                  for the period 1915-01-01 to 2001-12-31
  params/vic/   : VIC parameter files
    global_param.STEHE           : Global parameter file (the main VIC input file)
    global_param.STEHE.wb_output : Alternative version of global parameter file,
                                   as example of producing different output files
    global_param.STEHE.init_state: Alternative version of global parameter file,
                                   as example of starting from an initial state file
    global_param.STEHE.3hewb     : Alternative version of global parameter file,
                                   as example of an energy balance run at a
                                   3-hour time step
    snowbands.STEHE              : Snow band parameter file
    soil_param.STEHE             : Soil parameter file
    veglib.LDAS                  : Veg library file
    veg_param.STEHE              : Veg parameter file
  params/rout/  : Routing model parameter files
    rout_input.STEHE             : Main routing model input file
    STEHE.fdir                   : Flow direction file
    STEHE.fract                  : Fraction file
    STEHE.stnloc                 : Station location file
    STEHE.uh_s                   : Node unit hydrographs file
    UH.all                       : Grid cell unit hydrograph file
  state/        : VIC model state files
    STEHE.state_19481231         : Optional initial state file for use with a VIC run;
                                   this was created by running VIC for 3 years (1949-1951),
                                   in water-balance-only mode, starting from a default
                                   initial state
  results/vic/  : VIC output files
    default/                     : Results from global_param.STEHE
    wb_output/                   : Results from global_param.STEHE.wb_output
    init_state/                  : Results from global_param.STEHE.init_state
    3hewb/                       : Results from global_param.STEHE.3hewb
  results/rout/ : Routing model output files
  obs/          : Observed discharge records from Stehekin River at USGS gauge 12451000
    flow.STEHE.month.kaf         : Observed monthly discharge [kilo-acre-feet]
    flow.STEHE.month.cms         : Observed monthly discharge [m^3/sec]
    flow.STEHE.month.cfs         : Observed monthly discharge [ft^3/sec]
  tools/plot_flow_STEHE.scr      : Script for plotting observed and simulated monthly discharge
  plots/flow.STEHE.ps            : Postscript-format plot created by tools/plot_flow_STEHE.scr
  plots/flow.STEHE.jpg           : JPEG-format version of plots/flow.STEHE.ps

Instructions:

  Before running VIC or the routing model, you must first edit the following
files, to ensure that the paths in these files match the paths on your
machine:
  params/vic/global_param.STEHE
  params/vic/global_param.STEHE.3hewb
  params/vic/global_param.STEHE.init_state
  params/vic/global_param.STEHE.wb_output
  params/rout/rout_input.STEHE
  params/rout/STEHE.stnloc
For every occurrence of "./stehekin", you need to replace this with the
absolute path to this directory on your machine, for example
"/home/my_username/stehekin".

Notes:

1. To demonstrate a few different modes of VIC behavior, we have included 4
different global parameter files:

  * global_param.STEHE            : demonstrates a basic simulation in
                                    water-balance-only mode at a daily time
                                    step, writing to default output files.
  * global_param.STEHE.wb_output  : same as global_param.STEHE, but writes
                                    to custom output files containing only
                                    water budget terms.
  * global_param.STEHE.init_state : same as global_param.STEHE, but starts
                                    from an initial state file.
  * global_param.STEHE.3hewb      : demonstrates an energy balance run at
                                    a 3 hour time step.

All of these simulations are set up for years 1949-1951.  However, the forcing
data span 1949-01-01 through 2002-09-30.  You are free to lengthen the VIC
simulations as desired.

2. The routing input files are formatted to work with version 1.0 of the
routing model.  These may not work with other versions.  These files are
currently set up to use the output from the default VIC simulation
(global_param.STEHE), 1949-1951.  If you lengthen the VIC simulation,
and wish to rout the flow for this longer period, you will need to change
the range of dates listed in params/rout/rout_input.STEHE.

3. The plotting script tools/plot_flow_STEHE.scr is a c-shell script that
calls perl and various gmt commands.  If you do not have c-shell, perl, or
gmt installed on your system, this script will not work.
