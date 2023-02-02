<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


<h2>Installation Steps</h2>

<p>
</p>
<p>
In order to install OsTicket, you need to perform the following steps:

Download and install the following:
Web Platform Installer (IIS.net)
IIS 1.5.0 (IIS.net)
HeidiSQL (heidisql.com)
Enable IIS by going to the control panel, then to "uninstall a program," then to "Turn Windows features on or off." Select "internet information services" and click "OK." This will create an "inetpub" folder on disk C, which will host the web server that OsTicket will run on.
Download the web platform installer (you can get it from Google) and download MySQL and PHP up to 7.3 from within the web platform installer. Note that PHP will fail to install and must be manually downloaded.
Download the latest version of PHP from PHP.net, extract the folder, and copy it to the local disk in the "Program Files (x86)/PHP" folder.
Download and install PHP manager 1.5.0 for IIS 10 from IIS.net.
Open IIS (run as administrator), click on "PHP Manager," and under "PHP SETUP," click "register new PHP version." Search for the new PHP folder you just copied, open the folder, and select the "php-cgi.exe" file, then click "OK."
Download OsTicket from osticket.com, extract the folder, and copy the "upload" folder to the "wwwroot" folder inside the "inetpub" folder. Rename the "upload" folder to "osticket."
Refresh the IIS page and "osticket" should appear under "Sites." Click on "osticket," then click "Browse 80 (HTTP)," and the localhost/osticket/setup/ page will load.
On the webpage, you'll notice that the recommended extensions are not enabled. Use PHP Manager in IIS to enable the imap, intl, gd (if not already enabled), and opcache extensions. The apcu extension will not be in the list. Refresh the OsTicket page and only the last two options should be left. Click "continue."
To create the "ost-config.php" file, go to the "wwwroot" folder, then to "osticket," click "include," go to "ost-sampleconfig," copy and paste it in the same folder, and rename the copy to "ost-config." Right-click the file and click "Properties," then "Security," then "Users," then "Edit" to change the permission. Click "Users" again, under "Permission for Users," click "Full Control," then click "Apply," and then "OK." This will give you full access to OsTicket. Go back to OsTicket and click "continue."
Fill out the basic installation information for your help desk and admin user.
In the Database settings, you must first create the database. Use HeidiSQL (heidisql.com) to create a new database called "osticket." The username will be "root" and the password will be the one you chose earlier.
Fill in the database information in OsTicket. The MySQL will be "osticket," the username will be "root," and the password will be the one you chose. After entering the information, click "install."
