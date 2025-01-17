# zap2xml

This fork is for the sole purpose of building an ARM version of the image for use on a Raspberry Pi.

Docker container for zap2xml

This is zap2xml with Environment Variables driving the configuration. By default it runs every 12 hours to update your EPG data from zap2it

## Quick Run

`docker run -d --name zap2xml -v /xmltvdata:/data -e USERNAME=youremail@email.com -e PASSWORD=**password** -e OPT_ARGS="-I -D" -e XMLTV_FILENAME=xmltv.xml cddibble/zap2xml`

## Environment Settings

You can configure the following environment variables below:

### Required

- USERNAME - zap2it.com username
- PASSWORD - zap2it.com password

### Optional

- OPT_ARGS - additional command line arguments for zap2xml
- XMLTV_FILENAME - filename for your xmltv file (default: xmltv.xml)
- SLEEPTIME - time in seconds to wait before next run (default: 43200)

### Build ARM image

`docker buildx build -t cddibble/zap2xml:0.1 -t cddibble/zap2xml:latest --platform linux/arm64 .
GNU nano 5.4 /.cron/download_tv_guide.sh`
