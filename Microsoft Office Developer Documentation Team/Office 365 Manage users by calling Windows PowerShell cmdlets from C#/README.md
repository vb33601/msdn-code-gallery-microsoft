# Office 365: Manage users by calling Windows PowerShell cmdlets from C#
## Requires
- Visual Studio 2012
## License
- Apache License, Version 2.0
## Technologies
- Office 365
## Topics
- User Accounts
- Windows PowerShell
- management and monitoring tools
## Updated
- 02/27/2013
## Description

<p id="header"><span class="label">Summary:</span> This sample demonstrates how to use Windows PowerShell from a C# application to manage Office 365 user settings, and to create new user accounts. The sample requires you to have a user administrator account
 in an Office 365 organization, and that you install the Microsoft Online Services Sign-In Assistant, and the Microsoft Online Services Module for Windows PowerShell.</p>
<div id="mainSection">
<div id="mainBody">
<div class="introduction">
<p>&nbsp;</p>
</div>
<h1 class="heading">Description of the Sample</h1>
<div class="section" id="sectionSection0">This sample demonstrates how to use Windows PowerShell from a C# application to manage Office 365 user settings, and to create new user accounts. The sample requires you to have a user administrator account in an
 Office 365 organization, and that you install the Microsoft Online Services Sign-In Assistant, and the Microsoft Online Services Module for Windows PowerShell.</div>
<h1 class="heading">Prerequisites</h1>
<div class="section" id="sectionSection1">
<p>The following are required to be configured, or installed on the computer where you will build and use the sample:</p>
<ul>
<li>
<p>Office 365 Enterprise subscription.</p>
</li><li>
<p>User account credentials in the Office 365 organization having at least User Administrator privileges.</p>
</li><li>
<p>Windows 7 or Windows Server 2008 R2 with Windows PowerShell installed.</p>
</li><li>
<p>Visual Studio 2012 including components for Windows Forms applications installed.</p>
</li><li>
<p>.NET Framework 3.5 installed and enabled in Visual Studio.</p>
</li><li>
<p><a href="http://www.microsoft.com/en-in/download/details.aspx?id=28177" target="_blank">Microsoft Online Services Sign-In Assistant</a> installed.</p>
</li><li>
<p><a href="http://go.microsoft.com/fwlink/p/?LinkId=281794" target="_blank">Microsoft Online Services Module for Windows PowerShell</a> installed and configured as described in the following procedure.</p>
</li></ul>
<p>To run the sample you must enable remote control of Office 365 by performing the following steps.</p>
<h3 class="procedureSubHeading">Enable Office 365 remote control</h3>
<div class="subSection">
<ol>
<li>
<p>Locate the Microsoft Online Services Module for Windows PowerShell shortcut on the desktop.</p>
</li><li>
<p>Right-click the shortcut and choose <strong>Run as Administrator</strong>.</p>
</li><li>
<p>Click <strong>Yes</strong> if the <span class="ui">User Account Control</span> dialog box appears.</p>
</li><li>
<p>In the Windows PowerShell window, run the command <strong>Get-ExecutionPolicy</strong>.</p>
</li><li>
<p>If the command returns <strong>RemoteSigned</strong>, your computer is already configured properly to manage Office 365 remotely via Windows PowerShell.</p>
</li><li>
<p>If the command returned is not <strong>RemoteSigned</strong> (typically <strong>
Restricted</strong>), run the command <strong>Set-ExecutionPolicy RemoteSigned</strong> and then enter
<strong>Y</strong> when prompted.</p>
</li><li>
<p>In the Windows PowerShell window, run the command <strong>Get-ExecutionPolicy</strong> and verify that it returns
<strong>RemoteSigned</strong>.</p>
</li><li>
<p>Close the Windows PowerShell window.</p>
</li></ol>
</div>
</div>
<h1 class="heading">Key components of the sample</h1>
<div class="section" id="sectionSection2">
<p>The sample is a Windows Forms application that contains the following:</p>
<ul>
<li>
<p>An application main window that displays a grid listing Office 365 user accounts in the organization.</p>
</li><li>
<p>A dialog box to enter the administrator logon credentials.</p>
</li><li>
<p>A dialog box to set user information.</p>
</li></ul>
</div>
<h1 class="heading">Build the sample</h1>
<div class="section" id="sectionSection3">
<p>Before you begin using the sample, you should visit the Office 365 admin portal and verify the admin account's privileges. That account must have at least User management administrator privileges in the organization.</p>
<div class="subSection">
<ol>
<li>
<p>Open Visual Studio 2012.</p>
</li><li>
<p>Click <strong>File</strong>, <strong>Open</strong>, <strong>Project/Solution</strong>.</p>
</li><li>
<p>Navigate to the directory where you extracted the sample files.</p>
</li><li>
<p>In the <strong>O365_ManageUsers_cs</strong> folder, select <strong>O365_ManageUsers_cs.sln</strong> and click
<strong>OK</strong>.</p>
</li></ol>
</div>
<p>After the sample opens, the Visual Studio Solution Explorer should look like the following screen shot:</p>
<div class="caption">Figure 1. Solution Explorer.</div>
<br>
<img id="76590" src="http://i1.code.msdn.s-msft.com/office-365-manage-users-by-cfc96d5e/image/file/76590/1/o365.png" alt="Visual Studio 2012 Solution Explorer" width="295" height="273"></div>
<h1 class="heading">Run and test the sample</h1>
<div class="section" id="sectionSection4">
<div class="subSection">
<ol>
<li>
<p>In Visual Studio click <strong>Run</strong>, or press <strong>F5</strong> to build and start debugging the sample.</p>
</li><li>
<p>When the <span class="ui">Enter Credentials</span> dialog box appears as shown in the following screen shot, enter the administrator account user name and password and click
<strong>Login</strong>.</p>
<div class="caption">Figure 2. Enter Credentials Dialog Box.</div>
<br>
<img id="76591" src="http://i1.code.msdn.s-msft.com/office-365-manage-users-by-cfc96d5e/image/file/76591/1/o365psmanageusers-001.png" alt="Enter Credentials dialog" width="323" height="158">
</li><li>
<p>The main window is displayed in full-screen mode after you enter the credentials, as shown in the following screen shot. (User information is hidden in the image.)</p>
<div class="caption">Figure 3. Manage Users Dialog Box.</div>
<br>
<img id="76592" src="http://i1.code.msdn.s-msft.com/office-365-manage-users-by-cfc96d5e/image/file/76592/1/o365psmanageusers-003.png" alt="Sample main window with users obfuscated" width="878" height="463">
</li><li>
<p>To add a new user, click <strong>Add User</strong>. The <span class="ui">Add User</span> dialog box will appear, as shown in the following screen shot. Fill in the form fields and click the
<strong>Add User</strong> button.</p>
<div class="caption">Figure 4. Add User Dialog Box.</div>
<br>
<img id="76593" src="http://i1.code.msdn.s-msft.com/office-365-manage-users-by-cfc96d5e/image/file/76593/1/o365psmanageuser-004.png" alt="Code sample empty Add User dialog" width="407" height="297">
</li><li>
<p>To edit a user's settings. click the <strong>Edit</strong> button on the main window at the right of the row showing the user you want to edit. The
<span class="ui">Update User</span> dialog box has the same fields as the <span class="ui">
Add User</span> dialog box. Click <strong>Update User</strong> to save the changes.</p>
</li><li>
<p>To close the sample, click the <span class="ui">X</span> in the upper-right corner of the window.</p>
</li></ol>
</div>
</div>
<h1 class="heading">Troubleshooting</h1>
<div class="section" id="sectionSection5">
<p>The following table lists the common configuration and environment problems that prevent the sample from building or deploying successfully and how you can solve them.</p>
<div class="caption"></div>
<div class="tableSection">
<table cellspacing="2" cellpadding="5" width="50%" frame="lhs">
<tbody>
<tr>
<th>
<p>Problem</p>
</th>
<th>
<p>Solution</p>
</th>
</tr>
<tr>
<td>
<p>The <span class="ui">Login</span> dialog box reports &quot;Unable to authenticate your credentials.&quot;</p>
</td>
<td>
<p>Make sure that your user name is in the format: &lt;username&gt;@&lt;domain&gt; and that your password is correct.</p>
</td>
</tr>
<tr>
<td>
<p>Windows PowerShell or the application reports &quot;The term 'Connect-MsolService' is not recognized as the name of a cmdlet, function, script file, or operable program&hellip;.&quot;</p>
</td>
<td>
<p>Your user account doesn't have permission to run Windows PowerShell, or you have not installed the Microsoft Online Services Module for Windows PowerShell, or the execution policy is not set to RemoteSigned as described in the Prerequisites section.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h1 class="heading">Change log</h1>
<div class="section" id="sectionSection6">
<div class="caption"></div>
<div class="tableSection">
<table cellspacing="2" cellpadding="5" width="50%" frame="lhs">
<tbody>
<tr>
<th>
<p>Version</p>
</th>
<th>
<p>Date</p>
</th>
</tr>
<tr>
<td>
<p>First version</p>
</td>
<td>
<p>February, 28 2013</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h1 class="heading">Related content</h1>
<div class="section" id="sectionSection7">
<p><a href="http://msdn.microsoft.com/en-us/library/dd835506(v=vs.85).aspx" target="_blank">Windows PowerShell on MSDN</a></p>
<p><a href="http://onlinehelp.microsoft.com/en-us/office365-enterprises/hh125002.aspx" target="_blank">Windows PowerShell cmdlets for Office 365</a></p>
</div>
</div>
</div>
<p>&nbsp;</p>
