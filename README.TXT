--------------------------------------------------------------------------------
Liebert Global Products MIB
Version:    16
Date:       Thu Jan 23 13:01:33 EST 2020
Copyright <cp> 1999-2020 Liebert Corporation.  All Rights Reserved.
--------------------------------------------------------------------------------

--------------------------------------------------------------------------------
NOTE:
--------------------------------------------------------------------------------

Please consult the Quick Start Guide of your Liebert Power or Air Product for 
further information about using SNMP.  

The latest versions of User Manuals and MIBs are always available for download 
from www.liebert.com.


This distribution contains the MIB files used by most Liebert Products.

--------------------------------------------------------------------------------
INSTRUCTIONS FOR LOADING THE LIEBERT GLOBAL PRODUCTS MIB AND RFC1628 MIB:
--------------------------------------------------------------------------------

1)  Uncompress the compression file (either LgpMibDistribution_16_200123.ZIP or 
    LgpMibDistribution_16_200123.TAR) onto your NMS.

    This operation will yield twelve individual MIB files and this README.TXT
    file.

2)  Load/compile the individual MIB files onto your NMS in 
    the following order:

    LIEBERT_GP_REG.MIB            (Load First)
    LIEBERT_GP_AGENT.MIB
    LIEBERT_GP_COND.MIB
    LIEBERT_GP_CONTROLLER.MIB
    LIEBERT_GP_NOTIFY.MIB
    LIEBERT_GP_SYSTEM.MIB
    LIEBERT_GP_ENV.MIB
    LIEBERT_GP_PDU.MIB
    LIEBERT_GP_POWER.MIB
    LIEBERT_GP_FLEXIBLE.MIB
    LIEBERT_GP_FLEXIBLE_COND.MIB
    LIEBERT_GP_SRC.MIB            (Optional, only needed for thermal SRC product)       
    RFC1628_UPS_MIB.MIB           (Load Last)


    It is important that the MIB files be loaded in the correct
    order.
