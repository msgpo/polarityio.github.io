---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---

## Integrations

The Polarity Integration Framework provides a way to connect data sources to Polarity so that real-time notifications can be pushed to Polarity users based on data that is important to you.
    
In addition to connecting to existing datasources, the integration framework allows you customize how that data is displayed in the notification window.

## Available Integrations

* [VirusTotal](https://github.com/polarityio/virustotal)
* [CRITs](https://github.com/polarityio/crits)
* [Wikipedia](https://github.com/polarityio/wikipedia)
* [Google Maps](https://github.com/polarityio/google-maps)

## Installing Integrations

All Polarity Integrations are installed in a similar manner.  You can install integrations by either downloading a tar archive from the GitHub releases page of the integration you are interested in or by using git to clone the repo to your server.

### Installing via Release Download
 
Navigate to the [polarityio/virustotal releases page](https://github.com/polarityio/virustotal/releases).  Download the `tar.gz` file for the version of the integration you want to install (we typically recommend installing the latest version of the integration). Upload the `tar.gz` file to your Polarity Server. Move the `tar.gz` file to the Polarity Server integrations directory.

```bash
mv <filename> /app/polarity-server/integrations
```

Once the file has been moved, navigate to the integrations folder:

```bash
cd /app/polarity-server/integrations
```
  
Extract the tar file:

```bash
tar -xzvf <filename>
```

Navigate into the extracted folder for the new integration:

```bash
cd <filename>
```

Install the integration's dependencies:

```bash
npm install
```

Ensure the integration directory is owned by the `polarityd` user
 
```bash
chown -R polarityd:polarityd /app/polarity-server/integrations/virustotal
```

Restart your Polarity-Server

```bash
service polarityd restart
```

Navigate to the integrations page in Polarity-Web to configure the integration.

### Installing via GIT Clone

Navigate to the integrations folder:

```bash
cd /app/polarity-server/integrations
```

Clone a specific version of the integration repo you are interested in using git:

```bash
git clone --branch <version> https://github.com/polarityio/<integration-name>.git
```

As an example, if you wanted to install version `1.0.2-beta` of the `virustotal` integration you would use the command:

```bash
git clone --branch 1.0.2-beta https://github.com/polarityio/virustotal.git
```

Change into the integration directory

```bash
cd <integration-name>
```

Use `npm` to install the integration's dependencies

```bash
npm install
```

Ensure the integration directory is owned by the `polarityd` user

```bash
chown -R polarityd:polarityd /app/polarity-server/integrations/virustotal
```

Restart your Polarity-Server

```bash
service polarityd restart
```

Navigate to the integrations page in Polarity-Web to configure the integration

## Polarity

Polarity is a memory-augmentation platform that improves and accelerates analyst decision making.  For more information about the Polarity platform please see: 

https://polarity.io/ 