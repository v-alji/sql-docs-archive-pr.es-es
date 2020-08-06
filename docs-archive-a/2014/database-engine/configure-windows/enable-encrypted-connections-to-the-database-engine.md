---
title: Habilitar conexiones cifradas en el Motor de base de datos (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1653df929e3f8bc67158a0685ce07b8ba65de6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750141"
---
# <a name="enable-encrypted-connections-to-the-database-engine-sql-server-configuration-manager"></a><span data-ttu-id="ffc72-102">Habilitar conexiones cifradas en el motor de base de datos (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ffc72-102">Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="ffc72-103">En este tema se describe cómo habilitar conexiones cifradas para una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] mediante la especificación de un certificado para el [!INCLUDE[ssDE](../../includes/ssde-md.md)] utilizando el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffc72-103">This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="ffc72-104">El equipo servidor debe tener un certificado y el equipo cliente debe estar configurado para confiar en la entidad de certificación raíz del certificado.</span><span class="sxs-lookup"><span data-stu-id="ffc72-104">The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority.</span></span> <span data-ttu-id="ffc72-105">La puesta en servicio es el proceso de instalar un certificado mediante su importación en Windows.</span><span class="sxs-lookup"><span data-stu-id="ffc72-105">Provisioning is the process of installing a certificate by importing it into Windows.</span></span>  
  
 <span data-ttu-id="ffc72-106">El certificado debe estar emitido para la **Autenticación de servidor**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-106">The certificate must be issued for **Server Authentication**.</span></span> <span data-ttu-id="ffc72-107">El nombre del certificado debe ser el nombre de dominio completo (FQDN) del equipo.</span><span class="sxs-lookup"><span data-stu-id="ffc72-107">The name of the certificate must be the fully qualified domain name (FQDN) of the computer.</span></span>  
  
 <span data-ttu-id="ffc72-108">Los certificados se almacenan localmente para los usuarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="ffc72-108">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="ffc72-109">Si desea instalar un certificado para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]lo utilice, debe ejecutar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la misma cuenta de usuario que el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a menos que éste se esté ejecutando como LocalSystem, NetworkService o LocalService, en cuyo caso puede utilizar una cuenta administrativa.</span><span class="sxs-lookup"><span data-stu-id="ffc72-109">To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service unless the service is running as LocalSystem, NetworkService, or LocalService, in which case you may use an administrative account.</span></span>  
  
 <span data-ttu-id="ffc72-110">El cliente debe ser capaz de comprobar la propiedad del certificado utilizado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="ffc72-110">The client must be able to verify the ownership of the certificate used by the server.</span></span> <span data-ttu-id="ffc72-111">Si el cliente tiene el certificado de clave pública de la entidad de certificación que firmó el certificado del servidor, no es necesario realizar una mayor configuración.</span><span class="sxs-lookup"><span data-stu-id="ffc72-111">If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ffc72-112">Windows incluye los certificados de clave pública de muchas entidades de certificación.</span><span class="sxs-lookup"><span data-stu-id="ffc72-112">Windows includes the public key certificates of many certification authorities.</span></span> <span data-ttu-id="ffc72-113">Si el certificado del servidor lo firmó una entidad de certificación pública o privada para la que el cliente no tiene certificado de clave pública, debe instalar el certificado de clave pública de esta entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="ffc72-113">If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ffc72-114">Si desea utilizar el cifrado con un clúster de conmutación por error, debe instalar el certificado del servidor con el nombre DNS completo del servidor virtual en todos los nodos del clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ffc72-114">To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster.</span></span> <span data-ttu-id="ffc72-115">Por ejemplo, si tiene un clúster de dos nodos, con los nodos denominados test1 *\<your company>* . com y test2. *\<your company>* . com, y tiene un servidor virtual denominado virtsql, debe instalar un certificado para *\<your company>* virtsql. com en ambos nodos.</span><span class="sxs-lookup"><span data-stu-id="ffc72-115">For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes.</span></span> <span data-ttu-id="ffc72-116">Puede establecer el valor de la opción **ForceEncryption**en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-116">You can set the value of the **ForceEncryption**option to **Yes**.</span></span>  
  
 <span data-ttu-id="ffc72-117">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ffc72-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ffc72-118">**Para habilitar conexiones cifradas:**</span><span class="sxs-lookup"><span data-stu-id="ffc72-118">**To enable encrypted connections:**</span></span>  
  
     [<span data-ttu-id="ffc72-119">Proporcionar (instalar) un certificado en el servidor</span><span class="sxs-lookup"><span data-stu-id="ffc72-119">Provision (install) a certificate on the server</span></span>](#Provision)  
  
     [<span data-ttu-id="ffc72-120">Exportar el certificado del servidor</span><span class="sxs-lookup"><span data-stu-id="ffc72-120">Export the server certificate</span></span>](#Export)  
  
     [<span data-ttu-id="ffc72-121">Configurar el servidor de modo que acepte conexiones cifradas</span><span class="sxs-lookup"><span data-stu-id="ffc72-121">Configure the server to accept encrypted connections</span></span>](#ConfigureServerConnections)  
  
     [<span data-ttu-id="ffc72-122">Configurar el cliente para que solicite conexiones cifradas</span><span class="sxs-lookup"><span data-stu-id="ffc72-122">Configure the client to request encrypted connections</span></span>](#ConfigureClientConnections)  
  
     [<span data-ttu-id="ffc72-123">Cifrar una conexión desde SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ffc72-123">Encrypt a connection from SQL Server Management Studio</span></span>](#EncryptConnection)  
  
##  <a name="SSMSProcedure"></a>  
  
###  <a name="to-provision-install-a-certificate-on-the-server"></a><a name="Provision"></a> <span data-ttu-id="ffc72-124">Para proporcionar (instalar) un certificado en el servidor</span><span class="sxs-lookup"><span data-stu-id="ffc72-124">To provision (install) a certificate on the server</span></span>  
  
1.  <span data-ttu-id="ffc72-125">En el menú **Inicio** , haga clic en **Ejecutar**y, en el cuadro **abrir** , escriba `MMC` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-125">On the **Start** menu, click **Run**, and in the **Open** box, type `MMC` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="ffc72-126">En el menú **Archivo** de la consola MMC, haga clic en **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-126">In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="ffc72-127">En el cuadro de diálogo **Agregar o quitar complemento** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-127">In the **Add/Remove Snap-in** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="ffc72-128">En el cuadro de diálogo **Agregar un complemento independiente** , haga clic en **Certificados**y, después, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-128">In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.</span></span>  
  
5.  <span data-ttu-id="ffc72-129">En el cuadro de diálogo **Complemento de certificados** , haga clic en **Cuenta de equipo**y, después, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-129">In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="ffc72-130">En el cuadro de diálogo **Agregar un complemento independiente** , haga clic en **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="ffc72-130">In the **Add Standalone Snap-in** dialog box, click **Close.**</span></span>  
  
7.  <span data-ttu-id="ffc72-131">En el cuadro de diálogo **Agregar o quitar complemento** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-131">In the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="ffc72-132">En el complemento **Certificados** , expanda **Certificados**, expanda **Personal**. Tras ello, haga clic con el botón derecho en **Certificados**, seleccione **Todas las tareas**y, finalmente, haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-132">In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
9. <span data-ttu-id="ffc72-133">Finalice el **Asistente para importación de certificados**para agregar un certificado al equipo y cierre la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="ffc72-133">Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console.</span></span> <span data-ttu-id="ffc72-134">Para obtener más información acerca de cómo agregar un certificado a un equipo, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ffc72-134">For more information about adding a certificate to a computer, see your Windows documentation.</span></span>  
  
###  <a name="to-export-the-server-certificate"></a><a name="Export"></a> <span data-ttu-id="ffc72-135">Para exportar el certificado del servidor</span><span class="sxs-lookup"><span data-stu-id="ffc72-135">To export the server certificate</span></span>  
  
1.  <span data-ttu-id="ffc72-136">En el complemento **Certificados** , busque el certificado en la carpeta **Certificados** / **Personal** , haga clic con el botón derecho en **Certificado**, seleccione **Todas las tareas**y, luego, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-136">From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="ffc72-137">Complete el **Asistente para exportación de certificados**y guarde el archivo del certificado en una ubicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="ffc72-137">Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.</span></span>  
  
###  <a name="to-configure-the-server-to-accept-encrypted-connections"></a><a name="ConfigureServerConnections"></a> <span data-ttu-id="ffc72-138">Para configurar el servidor de modo que acepte conexiones cifradas</span><span class="sxs-lookup"><span data-stu-id="ffc72-138">To configure the server to accept encrypted connections</span></span>  
  
1.  <span data-ttu-id="ffc72-139">En el **Administrador de configuración de SQL Server**, expanda **Configuración de red de SQL Server**, haga clic con el botón derecho en **Protocolos de** _\<server instance>_ y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-139">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** _\<server instance>_, and then select**Properties**.</span></span>  
  
2.  <span data-ttu-id="ffc72-140">En el cuadro de diálogo **protocolos para** _\<instance name>_ **propiedades** , en la pestaña **certificado** , seleccione el certificado que desee en el menú desplegable del cuadro **certificado** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-140">In the **Protocols for**_\<instance name>_ **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop down for the **Certificate** box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ffc72-141">En la pestaña **Marcas** , en el cuadro **ForceEncryption** , seleccione **Sí**y, a continuación, haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ffc72-141">On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="ffc72-142">Reinicie el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffc72-142">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
###  <a name="to-configure-the-client-to-request-encrypted-connections"></a><a name="ConfigureClientConnections"></a> <span data-ttu-id="ffc72-143">Para configurar el cliente de modo que solicite conexiones cifradas</span><span class="sxs-lookup"><span data-stu-id="ffc72-143">To configure the client to request encrypted connections</span></span>  
  
1.  <span data-ttu-id="ffc72-144">Copie el certificado original o el archivo del certificado exportado en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="ffc72-144">Copy either the original certificate or the exported certificate file to the client computer.</span></span>  
  
2.  <span data-ttu-id="ffc72-145">En el equipo cliente, use el complemento **Certificados** para instalar el certificado raíz o el archivo del certificado exportado.</span><span class="sxs-lookup"><span data-stu-id="ffc72-145">On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.</span></span>  
  
3.  <span data-ttu-id="ffc72-146">En el panel de la consola, haga clic con el botón derecho en **Configuración de SQL Server Native Client**y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-146">In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ffc72-147">En la página **Marcas** , en el cuadro **Forzar cifrado de protocolo** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-147">On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.</span></span>  
  
###  <a name="to-encrypt-a-connection-from-sql-server-management-studio"></a><a name="EncryptConnection"></a><span data-ttu-id="ffc72-148">Para cifrar una conexión desde SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ffc72-148">To encrypt a connection from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="ffc72-149">En la barra de herramientas del Explorador de objetos, haga clic en **Conectar**y, a continuación, en **Motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-149">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="ffc72-150">En el cuadro de diálogo **Conectar al servidor** , rellene la información de conexión y, a continuación, haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-150">In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.</span></span>  
  
3.  <span data-ttu-id="ffc72-151">En la pestaña **Propiedades de conexión** , haga clic en **Cifrar conexión**.</span><span class="sxs-lookup"><span data-stu-id="ffc72-151">On the **Connection Properties** tab, click **Encrypt connection**.</span></span>  
  
  
