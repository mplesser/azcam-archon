# azcam-archon

*azcam-archon* is an *azcam* extension for STA Archon controllers. See http://www.sta-inc.net/archon/.

## Installation

`pip install azam-archon`

Or download from github: https://github.com/mplesser/azcam-archon.git.

## Example Code

The code below is for example only.

### Controller
    controller = ControllerArchon()
    controller.camserver.port = 4242
    controller.camserver.host = "10.0.2.10"
    controller.header.set_keyword("DEWAR", "ITL1", "Dewar name")
    controller.timing_file = os.path.join(
        azcam.db.projectfolder, "archon_code", "ITL1_STA3800C_Master.acf"
    )

### Exposure
    filetype = "MEF"
    exposure = ExposureArchon()
    exposure.fileconverter.set_detector_config(detector_sta3800)
    exposure.filetype = azcam.db.filetypes[filetype]
    exposure.image.filetype = azcam.db.filetypes[filetype]
    exposure.display_image = 1
    exposure.image.remote_imageserver_flag = 0
    exposure.add_extensions = 1
