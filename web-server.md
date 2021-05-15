
### <a name="web-server"></a> Web Server
This module is responsible for running web applications. The web applications to run cannot be another module's dependency. Think this one as a sandbox web server environment. By default, remote connections are refused as usual.

- Sandbox web server environment
- Main goal is to equip the master with the capability to test web applications in a wide range of environments.
- Therefore, this module consists of many devices as a member.
- Each device is featuring a distinct web server environment. Examples:
    - **LAMP**: Apache2 + Nginx server with PHP and MySQL installed and ready. Running a common Linux distro (CentOS, Ubuntu etc.)
    - **MEAN/MEVN/MERN**: CentOS with NodeJS, MongoDB, NPM, Yarn, Gulp.
    - **WIN**: Windows server with MSSQL installed
    - **RUBY**: Ruby, Node.js, Yarn, Gem, some Linux distro

- **[!]** After clean installation, master is tasked with creating an image of the prepared web service device instance. Cloning/Imaging tool candidates:
    - AOMEI
    - CloneZilla
    - Paragon
    - MondoRescue
    - Acronis
    
