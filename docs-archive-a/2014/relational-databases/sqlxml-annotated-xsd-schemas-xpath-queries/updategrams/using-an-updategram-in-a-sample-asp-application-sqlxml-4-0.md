---
title: Usar un diagrama en una aplicación ASP de ejemplo (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- ASP applications [SQLXML]
- Active Server Pages
- updategrams [SQLXML], ASP applications
ms.assetid: 10eff799-4c39-4b52-8b38-7ea6f68454a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 50dce61e5bd3111244defe9cc18e808580687185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674727"
---
# <a name="using-an-updategram-in-a-sample-asp-application-sqlxml-40"></a><span data-ttu-id="463e9-102">Utilizar un diagrama de actualización en una aplicación ASP de ejemplo (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="463e9-102">Using an Updategram in a Sample ASP Application (SQLXML 4.0)</span></span>
  <span data-ttu-id="463e9-103">Esta aplicación ASP (Páginas Active Server) le permite actualizar la información del cliente en la tabla Person.Contact de la base de datos de ejemplo AdventureWorks de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="463e9-103">This Active Server Pages (ASP) application allows you to update customer information in the Person.Contact table in the AdventureWorks sample database in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="463e9-104">La aplicación hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="463e9-104">The application does the following:</span></span>  
  
-   <span data-ttu-id="463e9-105">Solicita al usuario que escriba un identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="463e9-105">Asks the user to enter a contact ID.</span></span>  
  
-   <span data-ttu-id="463e9-106">Utiliza el valor de este identificador del cliente para ejecutar una plantilla a fin de recuperar la información de contacto de la tabla Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="463e9-106">Uses this customer ID value to execute a template to retrieve contact information from the Person.Contact table.</span></span>  
  
-   <span data-ttu-id="463e9-107">Muestra esta información utilizando un formulario HTML.</span><span class="sxs-lookup"><span data-stu-id="463e9-107">Displays this information by using an HTML form.</span></span>  
  
 <span data-ttu-id="463e9-108">A continuación, el usuario puede actualizar la información de contacto, pero no el identificador de contacto (puesto que ContactID es la clave principal).</span><span class="sxs-lookup"><span data-stu-id="463e9-108">The user can then update contact information but not the contact ID (because the ContactID is the primary key).</span></span> <span data-ttu-id="463e9-109">Después de que el usuario envíe la información, se ejecuta un diagrama de actualización y todos los parámetros del formulario se pasan al diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="463e9-109">After the user submits the information, an updategram is executed and all the form parameters are passed to the updategram.</span></span>  
  
 <span data-ttu-id="463e9-110">La siguiente plantilla es la primera plantilla (GetContact.xml).</span><span class="sxs-lookup"><span data-stu-id="463e9-110">The following template is the first template (GetContact.xml).</span></span> <span data-ttu-id="463e9-111">Guarde esta plantilla en el directorio asociado al nombre virtual del tipo `template`.</span><span class="sxs-lookup"><span data-stu-id="463e9-111">Save this template in the directory that is associated with the virtual name of `template` type.</span></span>  
  
```  
<root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <sql:header>  
      <sql:param name="cid"></sql:param>  
   </sql:header>  
   <sql:query>  
      SELECT  *   
      FROM    Person.Contact  
      WHERE   ContactID=@cid   
      FOR XML AUTO  
   </sql:query>  
</root>  
```  
  
 <span data-ttu-id="463e9-112">La siguiente plantilla es la segunda plantilla (UpdateContact.xml).</span><span class="sxs-lookup"><span data-stu-id="463e9-112">The following template is the second template (UpdateContact.xml).</span></span> <span data-ttu-id="463e9-113">Guarde esta plantilla en el directorio asociado al nombre virtual del tipo `template`.</span><span class="sxs-lookup"><span data-stu-id="463e9-113">Save this template in the directory that is associated with the virtual name of `template` type.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
   <updg:param name="cid"/>  
   <updg:param name="title" />  
   <updg:param name="firstname" />  
   <updg:param name="lastname" />  
   <updg:param name="emailaddress" />  
   <updg:param name="phone" />  
</updg:header>  
<updg:sync >  
   <updg:before>  
      <Person.Contact ContactID="$cid" />   
   </updg:before>  
   <updg:after>  
      <Person.Contact ContactID="$cid"   
       Title="$title"  
       FirstName="$firstname"  
       LastName="$lastname"  
       EmailAddress="$emailaddress"  
       Phone="$phone"/>  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="463e9-114">El siguiente código es la aplicación ASP (SampleASP.asp).</span><span class="sxs-lookup"><span data-stu-id="463e9-114">The following code is the ASP application (SampleASP.asp).</span></span> <span data-ttu-id="463e9-115">Guárdelo en el directorio asociado a una raíz virtual que cree con la utilidad Administrador de servicios Internet.</span><span class="sxs-lookup"><span data-stu-id="463e9-115">Save it in the directory that is associated with a virtual root that you create by using the Internet Services Manager utility.</span></span> <span data-ttu-id="463e9-116">(Esta raíz virtual no debe crearse con la utilidad Administración de directorios virtuales de IIS para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] porque Administración de directorios virtuales de IIS para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no puede obtener acceso a aplicaciones ASP ni identificarlas.)</span><span class="sxs-lookup"><span data-stu-id="463e9-116">(This virtual root is not created by using the IIS Virtual Directory Management for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utility because IIS Virtual Directory Management for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cannot access or identify ASP applications.).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="463e9-117">En el código, debe reemplazar "ServerName" por el nombre del servidor que ejecuta Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="463e9-117">In the code, you must replace "ServerName" with the name of the server running Microsoft Internet Information Services (IIS).</span></span>  
  
```  
<% LANGUAGE=VBSCRIPT %>  
<%  
  Dim ContactID  
  ContactID=Request.Form("cid")  
%>  
<html>  
<body>  
<%  
  'If a ContactID value is not yet provided, display this form.  
  if ContactID="" then  
%>  
<!-- If the ContactID has not been specified, display the form that allows users to enter an ID. -->  
<form action="AdventureWorksContacts.asp" method="POST">  
<br>  
Enter ContactID: <input type=text name="cid"><br>  
<input type=submit value="Submit this ID" ><br><br>  
<-- Otherwise, if a ContactID is entered, display the second part of the form where the user can change customer information. -->  
<%  
  else  
%>  
<form name="Contacts" action="http://localhost/AdventureWorks/Template/UpdateContact.xml" method="POST">  
You may update customer information below.<br><br>  
<!-- A comment goes here to separate the parts of the application or page. -->  
<br>  
<%  
  ' Load the document in the parser and extract the values to populate the form.  
    Set objXML=Server.CreateObject("MSXML2.DomDocument")  
    ObjXML.setProperty "ServerHTTPRequest", TRUE  
  
    objXML.async=False  
    objXML.Load("http://localhost/AdventureWorks/Template/GetContact.xml?cid=" & ContactID)  
    set objCustomer=objXML.documentElement.childNodes.Item(0)  
  
  ' In retrieving data from the database, if a value in the column is NULL there  
  '  is no attribute for the corresponding element. In this case,  
  ' skip the error generation and go to the next attribute.  
  
  On Error Resume Next  
  
  Response.Write "Contact ID: <input type=text readonly=true style='background-color:silver' name=cid value="""  
  Response.Write objCustomer.attributes(0).value  
  Response.Write """><br><br>"  
  
  Response.Write "Title: <input type=text name=title value="""  
  Response.Write objCustomer.attributes(1).value  
  Response.Write """><br><br>"  
  
  Response.Write "First Name: <input type=text name=firstname value="""  
  Response.Write objCustomer.attributes(2).value  
  Response.Write """><br>"  
  
  Response.Write "Last Name: <input type=text name=lastname value="""  
  Response.Write objCustomer.attributes(3).value  
  Response.Write """><br><br>"  
  
  Response.Write "Email Address: <input type=text name=emailaddress value="""  
  Response.Write objCustomer.attributes(4).value  
  Response.Write """><br><br>"  
  
  Response.Write "Phone: <input type=text name=phone value="""  
  Response.Write objCustomer.attributes(9).value  
  Response.Write """><br><br>"  
  
  set objCustomer=Nothing  
  Set objXML=Nothing  
%>  
<input type="submit" value="Submit this change" ><br><br>  
<input type=hidden name="contenttype" value="text/xml">  
<input type=hidden name="eeid" value="<%=ContactID%>"><br><br>  
<% end if %>  
  
</form>  
</body>  
</html>  
```  
  
## <a name="see-also"></a><span data-ttu-id="463e9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="463e9-118">See Also</span></span>  
 [<span data-ttu-id="463e9-119">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="463e9-119">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
