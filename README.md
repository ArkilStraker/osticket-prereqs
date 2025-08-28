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
<img width="730" height="485" alt="image" src="https://github.com/user-attachments/assets/5de249cd-c4cc-4137-bbc4-6a01336c5d83" />
<img width="523" height="506" alt="image" src="https://github.com/user-attachments/assets/1180b33a-0e59-401e-9963-798bfde3908e" />
<img width="542" height="370" alt="image" src="https://github.com/user-attachments/assets/b71f9f75-d3bf-46f7-b09e-8e1eab684dbb" />
<img width="527" height="297" alt="image" src="https://github.com/user-attachments/assets/8b97c9ad-a7cd-49ef-879b-023629b0480a" />


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

-IIS (Internet Information Services)

-PHP installed via Windows binaries

-FastCGI or certain PHP extensions

Many of the PHP builds for Windows (such as those from PHP.net or Web Platform Installer) rely on Microsoft’s C++ runtime libraries to function correctly. These libraries are provided through the Visual C++ Redistributable.

Why It's Required?
-It provides essential .DLL files like MSVCR110.dll or VCRUNTIME140.dll, which allow the PHP interpreter and associated modules to run.

-Without it, you may encounter errors or failed services when trying to load PHP, access MySQL, or even run osTicket's setup.

-It ensures that all native (compiled) PHP extensions or third-party libraries that osTicket depends on are supported.
<br />
<p>
 
<img width="491" height="383" alt="image" src="https://github.com/user-attachments/assets/43576f8c-fc52-4ada-bf84-f839532f0501" />
<img width="490" height="380" alt="image" src="https://github.com/user-attachments/assets/cc76b321-682d-4196-ae61-2d74000c4742" />
<img width="493" height="376" alt="image" src="https://github.com/user-attachments/assets/35692c69-7656-45e9-8325-4d46838bea69" />
<img width="497" height="377" alt="image" src="https://github.com/user-attachments/assets/996b69fb-9935-44e2-aaac-09de881424d9" />
<img width="494" height="371" alt="image" src="https://github.com/user-attachments/assets/c5db95a3-e034-4b00-80c7-7fe89e7d196a" />

</p>
<p>
MySQL Server acts as the database backbone of the osTicket system. It stores and manages all the structured data that osTicket uses to operate. This includes:

Ticket information

User accounts and departments

Email threads and internal notes

System settings and logs

When an end-user submits a ticket through the osTicket interface, that data is stored in the MySQL database. When staff members log in to view, update, or close tickets, osTicket retrieves and updates that information by communicating with MySQL Server using SQL queries.

Why MySQL Server Is Essential for osTicket

-It ensures secure, reliable storage of all help desk records.

-Enables efficient data retrieval, allowing fast ticket search, filtering, and reporting.

-Works seamlessly with PHP (which osTicket is built on) and Apache or IIS servers.

-Supports scalability; as the helpdesk grows, MySQL can handle increasing amounts of data and users.
</p>
<br />
<p>
  
<img width="642" height="307" alt="image" src="https://github.com/user-attachments/assets/f0145a32-a04e-4bbe-b77c-ceb55f964241" />

</p>
<p>
Renaming the upload folder to osTicket within C:\inetpub\wwwroot sets up the application in a clearly named directory and allows IIS to recognize and serve the osTicket helpdesk interface from a logical and accessible web path (e.g., http://localhost/osTicket).
</p>
<br />
