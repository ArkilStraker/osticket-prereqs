<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11 Pro</b> (21H2)

<h2>List of Prerequisites</h2>

- Enable Internet Information Services (IIS)
- Install web platform installer
- Install c++ redeistributable
- Install MySQL and set up user name and password
- Configure pernissions and install osTicket

<h2>Installation Steps</h2>
<p>
<img width="411" height="366" alt="image" src="https://github.com/user-attachments/assets/1ce194c0-1bb9-410e-92a9-834d092f3b68" />

</p>
<p>
IIS (Internet Information Services) is the web server used to host and run osTicket when deploying the system on a Windows-based environment. It acts as the bridge between users and the osTicket application, handling all web traffic and delivering the PHP-based content through the browser.
</p>
<br />

<p>
  <img width="495" height="407" alt="image" src="https://github.com/user-attachments/assets/ff754e25-3f0a-497c-83f7-4758d4943d3f" />

</p>
<p>
Installing PHP Manager for Internet Information Services (IIS). PHP Manager is a Windows IIS (Internet Information Services) extension that helps you easily manage PHP settings and configurations. It provides a graphical interface in the IIS Manager that makes PHP management more user-friendly.
</p>
<br />

<p>
<img width="429" height="346" alt="image" src="https://github.com/user-attachments/assets/b707311f-a9bd-4a13-9dfb-a7ba29b584de" /><img width="425" height="457" alt="image" src="https://github.com/user-attachments/assets/137bc5e4-c374-477c-8a7f-40acf9a9b829" />
<img width="407" height="375" alt="image" src="https://github.com/user-attachments/assets/9b2e37d2-5997-478d-b815-809809806a4e" /><img width="441" height="302" alt="image" src="https://github.com/user-attachments/assets/73d86a06-0220-4b70-aa29-84367a60875d" />
</p>
<p>
Registering PHP from within IIS” means configuring Internet Information Services (IIS) to recognize and process PHP files by linking it to the PHP executable (php-cgi.exe). This step is essential when hosting PHP-based applications—such as osTicket—on a Windows server, allowing IIS to correctly interpret and serve .php pages through the FastCGI module.
</p>
<br />

<p>
  <img width="495" height="385" alt="image" src="https://github.com/user-attachments/assets/4a5b54a3-0ca3-413b-a8de-fac8929bb112" />
</p>
<p>
Rewrite module refers to the Apache “mod_rewrite” module or URL Rewrite module for IIS; depending on whether you're installing osTicket on Linux/Apache or Windows/IIS. The rewrite module allows the web server to process clean, user-friendly URLs (e.g., example.com/support/ticket/123 instead of support.php?id=123). osTicket uses it for routing and SEO-friendly URLs.
</p>
<br />

<p>
  <img width="479" height="293" alt="image" src="https://github.com/user-attachments/assets/1f924af0-3ab7-4b17-b611-3c7f815ef7ab" />
</p>
<p>
The Microsoft Visual C++ Redistributable is a required runtime component for running certain features of osTicket on Windows-based servers, especially when osTicket is deployed using:

- IIS (Internet Information Services)
- PHP installed via Windows binaries
- FastCGI or certain PHP extensions

Many of the PHP builds for Windows (such as those from PHP.net or Web Platform Installer) rely on Microsoft’s C++ runtime libraries to function correctly. These libraries are provided through the Visual C++ Redistributable.

Why It's Required?

- It provides essential .DLL files like MSVCR110.dll or VCRUNTIME140.dll, which allow the PHP interpreter and associated modules to run.
- Without it, you may encounter errors or failed services when trying to load PHP, access MySQL, or even run osTicket's setup.
- It ensures that all native (compiled) PHP extensions or third-party libraries that osTicket depends on are supported.
</p>
<br />

<p>
<img width="492" height="345" alt="image" src="https://github.com/user-attachments/assets/018e259b-3762-4b86-9cf7-7ffbd7118381" /><img width="444" height="330" alt="image" src="https://github.com/user-attachments/assets/c47e4d4a-82f0-4c54-97ae-aa88f080fad2" />
<img width="463" height="330" alt="image" src="https://github.com/user-attachments/assets/fdccd19e-1b15-4b26-a3c7-6fe20f6480b8" /><img width="456" height="342" alt="image" src="https://github.com/user-attachments/assets/84f37bf6-3c45-4078-9919-f1da671032ae" />
<img width="487" height="347" alt="image" src="https://github.com/user-attachments/assets/25fd8539-37c5-4082-becb-ed8e310afc74" />
</p>
<p>
MySQL Server acts as the database backbone of the osTicket system. It stores and manages all the structured data that osTicket uses to operate. This includes:

- Ticket information

- User accounts and departments

- Email threads and internal notes

- System settings and logs

When an end-user submits a ticket through the osTicket interface, that data is stored in the MySQL database. When staff members log in to view, update, or close tickets, osTicket retrieves and updates that information by communicating with MySQL Server using SQL queries.

Why MySQL Server Is Essential for osTicket

- It ensures secure, reliable storage of all help desk records.

- Enables efficient data retrieval, allowing fast ticket search, filtering, and reporting.

- Works seamlessly with PHP (which osTicket is built on) and Apache or IIS servers.

- Supports scalability; as the helpdesk grows, MySQL can handle increasing amounts of data and users.
</p>
<br />

<p> 
<img width="642" height="307" alt="image" src="https://github.com/user-attachments/assets/f0145a32-a04e-4bbe-b77c-ceb55f964241" />
</p>
<p>
Renaming the upload folder to osTicket within C:\inetpub\wwwroot sets up the application in a clearly named directory and allows IIS to recognize and serve the osTicket helpdesk interface from a logical and accessible web path (e.g., http://localhost/osTicket).
</p>
<br />

<p>  
<img width="355" height="546" alt="image" src="https://github.com/user-attachments/assets/c8b22cd2-89ca-4a67-9816-c17ead600263" /><img width="504" height="400" alt="image" src="https://github.com/user-attachments/assets/a5e11a07-e08d-4cad-92cb-c464f0894f6b" />
</p>
<p>
Enabling PHP intl and imap Extensions
These extensions are required by osTicket for multilingual support and email fetching.
They are enabled by editing the php.ini file to activate extension=intl and extension=imap, followed by restarting IIS. This allows the osTicket system to fully support global users and create tickets from incoming emails.
</p>
<br />

<p>  
<img width="521" height="401" alt="image" src="https://github.com/user-attachments/assets/78dfef38-3e23-4a97-8f8b-7231805d337f" /><img width="323" height="246" alt="image" src="https://github.com/user-attachments/assets/6f3be5a7-8a63-4cfc-873f-2372ddb15085" />
</p>
<p>
HeidiSQL is a powerful and user-friendly database management tool used to connect to MySQL, MariaDB, PostgreSQL, and other databases. In projects like osTicket, HeidiSQL allows developers and administrators to browse tables, run queries, manage data, and troubleshoot issues—all from a clean and efficient graphical interface.
</p>
<br />

<p>
<img width="469" height="562" alt="image" src="https://github.com/user-attachments/assets/0b373a9a-5986-40da-9eb7-820495872d70" /><img width="518" height="597" alt="image" src="https://github.com/user-attachments/assets/1bced936-2af5-46ab-a6b2-26d1e4afbecf" />
</p>
<p>
The osTicket Installer is a web-based setup wizard that guides users through the installation and initial configuration of the osTicket helpdesk system. After uploading the osTicket files to a web server (such as IIS or Apache), the installer walks the user through verifying system requirements, connecting to the database, and creating the admin account needed to launch the helpdesk.
</p>
<br />

<p>
<img width="398" height="288" alt="image" src="https://github.com/user-attachments/assets/44550b57-2442-4b74-9577-e913afe104b3" />
</p>
<p>
The Admin User in osTicket holds the highest level of access within the system. This account can configure, customize, and maintain the entire helpdesk, including user permissions, system settings, ticket workflows, and automation. This role is essential for initial configuration, ongoing maintenance, and ensuring the helpdesk operates securely and efficiently.
</p>
<br />
