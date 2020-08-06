---
title: Configurar IIS 7 para la sincronización web | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- IIS 7 server configuration [SQL Server replication]
- Web synchronization, IIS 7 servers
ms.assetid: c201fe2c-0a76-44e5-a233-05e14cd224a6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65b5aa1ea0d314a9675b1c1b90b688d2990e6d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678169"
---
# <a name="configure-iis-7-for-web-synchronization"></a><span data-ttu-id="b8321-102">Configurar IIS 7 para la sincronización web</span><span class="sxs-lookup"><span data-stu-id="b8321-102">Configure IIS 7 for Web Synchronization</span></span>
  <span data-ttu-id="b8321-103">Los procedimientos descritos en este tema le guiarán a través del proceso de configurar manualmente [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) versión 7 y superior para su uso con la sincronización web en la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="b8321-103">The procedures in this topic will guide you through the process of manually configuring [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) version 7 and higher for use with Web synchronization for merge replication.</span></span> 
  
 <span data-ttu-id="b8321-104">La configuración de IIS 7 es el primero de los tres pasos necesarios para habilitar la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="b8321-104">Configuring IIS 7 is the first of three steps needed to enable Web synchronization.</span></span>  
  
 <span data-ttu-id="b8321-105">Para obtener información general sobre todo el proceso de configuración, vea [Configurar sincronización web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="b8321-105">For an overview of the entire configuration process, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8321-106">Asegúrese de que la aplicación solo utilice [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] o versiones posteriores, y de que no haya versiones anteriores de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] instaladas en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-106">Make sure that your application uses only [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] or later versions, and that earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] are not installed on the IIS server.</span></span> <span data-ttu-id="b8321-107">Las versiones anteriores de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] pueden producir errores, por ejemplo: "El formato de un mensaje durante la sincronización web no es válido.</span><span class="sxs-lookup"><span data-stu-id="b8321-107">Earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] can cause errors, such as: "The format of a message during Web synchronization was invalid.</span></span> <span data-ttu-id="b8321-108">Asegúrese de que los componentes de replicación se han configurado correctamente en el servidor web."</span><span class="sxs-lookup"><span data-stu-id="b8321-108">Ensure that replication components are properly configured at the Web server."</span></span>  
  
 <span data-ttu-id="b8321-109">Para utilizar la sincronización web, debe configurar IIS 7 mediante los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="b8321-109">To use Web synchronization, you must configure IIS 7 by completing the following steps.</span></span> <span data-ttu-id="b8321-110">Cada paso se describe detalladamente en este tema.</span><span class="sxs-lookup"><span data-stu-id="b8321-110">Each step is described in detail in this topic.</span></span>  
  
1.  <span data-ttu-id="b8321-111">Instale y configure Escucha de replicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el equipo en el que se ejecuta IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-111">Install and configure the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener on the computer that is running IIS.</span></span>  
  
2.  <span data-ttu-id="b8321-112">Configure SSL (Capa de sockets seguros).</span><span class="sxs-lookup"><span data-stu-id="b8321-112">Configure Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="b8321-113">SSL es necesario para establecer comunicaciones entre IIS y todos los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="b8321-113">SSL is required for communication between IIS and all subscribers.</span></span>  
  
3.  <span data-ttu-id="b8321-114">Configure la autenticación IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-114">Configure IIS authentication.</span></span>  
  
4.  <span data-ttu-id="b8321-115">Configure una cuenta y establezca permisos para la Escucha de replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8321-115">Configure an account and set permissions for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener.</span></span>  
  
## <a name="installing-the-sql-server-replication-listener"></a><span data-ttu-id="b8321-116">Instalar la Escucha de replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8321-116">Installing the SQL Server Replication Listener</span></span>  

<span data-ttu-id="b8321-117">La sincronización web es compatible con IIS, a partir de la versión 5.0.</span><span class="sxs-lookup"><span data-stu-id="b8321-117">Web synchronization is supported on IIS, beginning with version 5.0.</span></span> <span data-ttu-id="b8321-118">El Asistente de configuración de sincronización web de IIS versión 5 y 6 no está disponible con IIS versión 7.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="b8321-118">The Configure Web Synchronization Wizard of IIS version 5 and 6, is not available with IIS version 7.0 and higher.</span></span> <span data-ttu-id="b8321-119">**A partir de SQL Server 2012, para usar el componente de sincronización web en el servidor IIS, debe instalar SQL Server con replicación. Puede ser la edición gratuita de SQL Server Express.**</span><span class="sxs-lookup"><span data-stu-id="b8321-119">**Beginning with SQL Server 2012, to use the web sync component on IIS server, you should install SQL Server with replication. This can be the free SQL Server Express edition.**</span></span>
  
#### <a name="to-install-and-configure-the-sql-server-replication-listener"></a><span data-ttu-id="b8321-120">Para instalar y configurar la Escucha de replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8321-120">To install and configure the SQL Server Replication Listener</span></span>  
  
1. <span data-ttu-id="b8321-121">Instale la replicación de SQL Server en el equipo de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-121">Install SQL Server replication on the IIS computer.</span></span>

2.  <span data-ttu-id="b8321-122">Cree un directorio de archivos para replisapi.dll en el equipo que ejecute IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-122">Create a new file directory for replisapi.dll on the computer that is running IIS.</span></span> <span data-ttu-id="b8321-123">Puede crear el directorio donde quiera, pero se recomienda crearlo en el directorio \<*drive*>:\Inetpub.</span><span class="sxs-lookup"><span data-stu-id="b8321-123">You can create the directory wherever you want, but we recommend that you create the directory under the \<*drive*>:\Inetpub directory.</span></span> <span data-ttu-id="b8321-124">Por ejemplo, cree el directorio \<*drive*>:\Inetpub\SQLReplication\\.</span><span class="sxs-lookup"><span data-stu-id="b8321-124">For example, create the directory \<*drive*>:\Inetpub\SQLReplication\\.</span></span>  
  
3.  <span data-ttu-id="b8321-125">Copie replisapi.dll del directorio [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ al directorio de archivos que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="b8321-125">Copy replisapi.dll from the directory [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ to the file directory that you created in step 1.</span></span>  
  
4.  <span data-ttu-id="b8321-126">Registre el archivo replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="b8321-126">Register replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="b8321-127">Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-127">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="b8321-128">En el cuadro **abrir** , escriba `cmd` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-128">In the **Open** box, enter `cmd`, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="b8321-129">En el directorio creado en el paso 1, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b8321-129">In the directory created in step 1, execute the following command:</span></span>  
  
         `regsvr32 replisapi.dll`  
  
5.  <span data-ttu-id="b8321-130">Cree un nuevo sitio web para la replicación, o bien utilice un sitio existente.</span><span class="sxs-lookup"><span data-stu-id="b8321-130">Create a new Web site for replication or use an existing site.</span></span> <span data-ttu-id="b8321-131">Los componentes de la replicación tendrán acceso al sitio web durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="b8321-131">This Web site will be accessed by replication components during synchronization.</span></span> <span data-ttu-id="b8321-132">En los procedimientos de este tema se asume que se utiliza el sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b8321-132">Procedures in this topic will assume the Default Web Site.</span></span> <span data-ttu-id="b8321-133">Para obtener más información acerca de cómo crear sitios web, vea la documentación de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-133">For more information about how to create Web sites, see the IIS documentation</span></span>  
  
6.  <span data-ttu-id="b8321-134">Cree un directorio virtual en IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-134">Create a virtual directory in IIS.</span></span> <span data-ttu-id="b8321-135">El directorio virtual se debe crear en el sitio web creado en el paso 4 y asignarse al directorio creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="b8321-135">The virtual directory should be created under the Web site that you created in step 4 and map it to the directory created in step 1.</span></span> <span data-ttu-id="b8321-136">Asigne a este directorio el mínimo de permisos posible.</span><span class="sxs-lookup"><span data-stu-id="b8321-136">Be as restrictive as possible when you assign permissions to this directory.</span></span> <span data-ttu-id="b8321-137">Debe seleccionar los permisos **Lectura** y **Ejecutar** como mínimo.</span><span class="sxs-lookup"><span data-stu-id="b8321-137">You must select at least **Read** and **Execute** permissions.</span></span>  
  
    1.  <span data-ttu-id="b8321-138">En **Administrador de Internet Information Services (IIS)** , en el panel **Conexiones** , haga clic con el botón secundario en **Sitio web predeterminado**y, a continuación, seleccione **Agregar directorio virtual**.</span><span class="sxs-lookup"><span data-stu-id="b8321-138">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, right-click **Default Web Site**, and then select **Add Virtual Directory**.</span></span>  
  
    2.  <span data-ttu-id="b8321-139">En **alias**, escriba `SQLReplication` .</span><span class="sxs-lookup"><span data-stu-id="b8321-139">For **Alias**, enter `SQLReplication`.</span></span>  
  
    3.  <span data-ttu-id="b8321-140">En **Ruta de acceso física**, escriba **\<drive>:\Inetpub\SQLReplication\\** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-140">For **Physical Path**, enter **\<drive>:\Inetpub\SQLReplication\\**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b8321-141">Configure IIS para permitir la ejecución de replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="b8321-141">Configure IIS to enable replisapi.dll to execute.</span></span>  
  
    1.  <span data-ttu-id="b8321-142">En **Administrador de Internet Information Services (IIS)** , haga clic en **Sitio web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="b8321-142">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="b8321-143">En el panel del centro, haga clic en **Asignaciones de controlador**.</span><span class="sxs-lookup"><span data-stu-id="b8321-143">In the center pane, click **Handler Mappings**.</span></span>  
  
    3.  <span data-ttu-id="b8321-144">En el panel **Acciones** , haga clic en **Agregar asignación de módulo**.</span><span class="sxs-lookup"><span data-stu-id="b8321-144">In the **Actions** pane, click **Add Module Mapping**.</span></span>  
  
    4.  <span data-ttu-id="b8321-145">En ruta de acceso de la **solicitud** , escriba `replisapi.dll` .</span><span class="sxs-lookup"><span data-stu-id="b8321-145">For **Request** Path, enter `replisapi.dll`.</span></span>  
  
    5.  <span data-ttu-id="b8321-146">En la lista desplegable **Módulo** , seleccione **IsapiModule**.</span><span class="sxs-lookup"><span data-stu-id="b8321-146">From the **Module** drop-down list, select **IsapiModule**.</span></span>  
  
    6.  <span data-ttu-id="b8321-147">En **Ejecutable**, escriba **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span><span class="sxs-lookup"><span data-stu-id="b8321-147">For **Executable**, enter **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span></span>  
  
    7.  <span data-ttu-id="b8321-148">En **Nombre**, escriba `Replisapi`.</span><span class="sxs-lookup"><span data-stu-id="b8321-148">For **Name**, enter `Replisapi`.</span></span>  
  
    8.  <span data-ttu-id="b8321-149">Haga clic en el botón **Restricciones de solicitudes** , en la pestaña **Acceso** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-149">Click the **Request Restrictions** button, click the **Access** tab, and then click **Execute**.</span></span>  
  
    9. <span data-ttu-id="b8321-150">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Restricciones de solicitudes** y, a continuación, haga clic de nuevo en **Aceptar** para cerrar el cuadro de diálogo **Agregar asignación de módulo** .</span><span class="sxs-lookup"><span data-stu-id="b8321-150">Click **OK** to close the **Request Restrictions** dialog box, and then click **OK** again to close the **Add Module Mapping** dialog box.</span></span> <span data-ttu-id="b8321-151">Cuando se le pida que permita la extensión ISAPI, haga clic en **Sí** para agregar la extensión.</span><span class="sxs-lookup"><span data-stu-id="b8321-151">When you are prompted to allow the ISAPI extension, click **Yes** to add the extension.</span></span>  
  
    10. <span data-ttu-id="b8321-152">Compruebe que Replisapi.dll está en la lista, en las asignaciones de controlador **Habilitadas** .</span><span class="sxs-lookup"><span data-stu-id="b8321-152">Verify that Replisapi.dll is listed under the **Enabled** handler mappings.</span></span> <span data-ttu-id="b8321-153">Si está en la lista **Deshabilitadas** , haga clic con el botón secundario en la entrada de Replisapi y, a continuación, haga clic en **Modificar permisos de características**.</span><span class="sxs-lookup"><span data-stu-id="b8321-153">If it is in the **Disabled** list, right-click the Replisapi entry and then click **Edit Feature Permissions**.</span></span> <span data-ttu-id="b8321-154">Active la casilla **Ejecutar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-154">Check the **Execute** box, and then click **OK**.</span></span>  
  
## <a name="configuring-iis-authentication"></a><span data-ttu-id="b8321-155">Configurar la autenticación IIS</span><span class="sxs-lookup"><span data-stu-id="b8321-155">Configuring IIS Authentication</span></span>  
 <span data-ttu-id="b8321-156">Cuando los equipos suscriptores se conectan a IIS, IIS debe autenticarlos para que puedan tener acceso a los recursos y procesos.</span><span class="sxs-lookup"><span data-stu-id="b8321-156">When subscriber computers connect to IIS, IIS must authenticate the subscribers before they can access resources and processes.</span></span> <span data-ttu-id="b8321-157">La autenticación se puede aplicar a todo el sitio web o al directorio virtual que ha creado.</span><span class="sxs-lookup"><span data-stu-id="b8321-157">Authentication can be applied to the whole Web site or to the virtual directory that you created.</span></span>  
  
 <span data-ttu-id="b8321-158">Se recomienda usar la autenticación básica con SSL.</span><span class="sxs-lookup"><span data-stu-id="b8321-158">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="b8321-159">SSL es necesario, independientemente del tipo de autenticación que se utilice.</span><span class="sxs-lookup"><span data-stu-id="b8321-159">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
 <span data-ttu-id="b8321-160">Se recomienda usar la autenticación básica con SSL.</span><span class="sxs-lookup"><span data-stu-id="b8321-160">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="b8321-161">SSL es necesario, independientemente del tipo de autenticación que se utilice.</span><span class="sxs-lookup"><span data-stu-id="b8321-161">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
#### <a name="to-configure-iis-authentication"></a><span data-ttu-id="b8321-162">Para configurar la autenticación IIS</span><span class="sxs-lookup"><span data-stu-id="b8321-162">To Configure IIS Authentication</span></span>  
  
1.  <span data-ttu-id="b8321-163">En **Administrador de Internet Information Services (IIS)** , haga clic en **Sitio web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="b8321-163">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
2.  <span data-ttu-id="b8321-164">En el panel central, haga doble clic en **Autenticación**.</span><span class="sxs-lookup"><span data-stu-id="b8321-164">In the middle pane, double-click **Authentication**.</span></span>  
  
3.  <span data-ttu-id="b8321-165">Haga clic con el botón secundario en Autenticación anónima y, a continuación, elija Deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="b8321-165">Right-click Anonymous Authentication, and then choose Disable.</span></span>  
  
4.  <span data-ttu-id="b8321-166">Haga clic con el botón secundario en Autenticación básica y, a continuación, elija Habilitar.</span><span class="sxs-lookup"><span data-stu-id="b8321-166">Right-click Basic Authentication, and then choose Enable.</span></span>  
  
## <a name="configuring-secure-sockets-layer"></a><span data-ttu-id="b8321-167">Configurar la Capa de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="b8321-167">Configuring Secure Sockets Layer</span></span>  
 <span data-ttu-id="b8321-168">Para configurar SSL, especifique un certificado para que lo utilice el equipo en el que se ejecuta IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-168">To configure SSL, specify a certificate to be used by the computer running IIS.</span></span> <span data-ttu-id="b8321-169">La sincronización web para la replicación de mezcla es compatible con el uso de certificados de servidor, pero no de certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="b8321-169">Web synchronization for merge replication supports using server certificates, but not client certificates.</span></span> <span data-ttu-id="b8321-170">Para configurar IIS para implementación, primero debe obtener un certificado por parte de una entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="b8321-170">To configure IIS for deployment, you must first obtain a certificate from a certification authority (CA).</span></span> <span data-ttu-id="b8321-171">Para obtener más información acerca de los certificados, vea la documentación de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-171">For more information about certificates, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="b8321-172">Cuando el certificado esté instalado, debe asociarlo al sitio web que utiliza la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="b8321-172">After you install the certificate, you must associate the certificate with the Web site that is used by Web synchronization.</span></span> <span data-ttu-id="b8321-173">En el caso las tareas de desarrollo y pruebas, puede especificar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="b8321-173">For development and testing, you can specify a self-signed certificate.</span></span> <span data-ttu-id="b8321-174">IIS 7 puede crear un certificado y registrarlo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b8321-174">IIS 7 can create a certificate for you and register it on your computer.</span></span>  
  
 <span data-ttu-id="b8321-175">La diferencia entre las implementaciones para producción y los procedimientos descritos aquí es que en producción y las pruebas de pre-producción se utilizaría un certificado emitido por una entidad de certificación en lugar de un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="b8321-175">The difference between deploying for production and the procedures given here is that in production and pre-production testing, you would use a certificate issued by a CA instead of a self-signed certificate.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8321-176">No es recomendable utilizar un certificado autofirmado en una instalación de producción.</span><span class="sxs-lookup"><span data-stu-id="b8321-176">A self-signed certificate is not recommended for a production installation.</span></span> <span data-ttu-id="b8321-177">Los certificados autofirmados no son seguros.</span><span class="sxs-lookup"><span data-stu-id="b8321-177">Self-signed certificates are not secure.</span></span> <span data-ttu-id="b8321-178">Utilice certificados autofirmados solo en instalaciones de desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="b8321-178">Use self-signed certificates for development and testing only.</span></span>  
  
 <span data-ttu-id="b8321-179">Para configurar SSL, debe realizar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b8321-179">To configure SSL, you will perform the following steps:</span></span>  
  
1.  <span data-ttu-id="b8321-180">Configure el sitio web para requiera SSL y pase por alto los certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="b8321-180">Configure the Web site to require SSL and ignore client certificates.</span></span>  
  
2.  <span data-ttu-id="b8321-181">Obtenga un certificado de una entidad de certificación o cree un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="b8321-181">Obtain a certificate from a CA or create a self-signed certificate.</span></span>  
  
3.  <span data-ttu-id="b8321-182">Enlace el certificado al sitio web de replicación.</span><span class="sxs-lookup"><span data-stu-id="b8321-182">Bind the certificate to the replication Web site.</span></span>  
  
#### <a name="to-require-ssl-security-for-a-web-site"></a><span data-ttu-id="b8321-183">Para exigir la seguridad SSL en un sitio web</span><span class="sxs-lookup"><span data-stu-id="b8321-183">To require SSL security for a Web site</span></span>  
  
1.  <span data-ttu-id="b8321-184">En el **Administrador de Internet Information Services (IIS)** , expanda el nodo de servidor local y, a continuación, haga clic en **Sitio web predeterminado** (o el sitio de sincronización web si es diferente del sitio web predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b8321-184">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="b8321-185">En el panel central, haga doble clic en **Configuración SSL**.</span><span class="sxs-lookup"><span data-stu-id="b8321-185">In the middle pane, double-click **SSL Settings**.</span></span>  
  
3.  <span data-ttu-id="b8321-186">Active la opción **Requerir SSL** .</span><span class="sxs-lookup"><span data-stu-id="b8321-186">Check the **Require SSL** option.</span></span> <span data-ttu-id="b8321-187">En **Certificados cliente**, compruebe que el botón **Omitir** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b8321-187">Under **Client certificates**, verify that the **Ignore** button is selected.</span></span>  
  
#### <a name="to-create-a-self-signed-certificate-for-testing"></a><span data-ttu-id="b8321-188">Para crear un certificado autofirmado para pruebas</span><span class="sxs-lookup"><span data-stu-id="b8321-188">To create a self-signed certificate for testing</span></span>  
  
1.  <span data-ttu-id="b8321-189">En el **Administrador de Internet Information Services (IIS)** , haga clic en el nodo de servidor local y, a continuación, en el panel del centro, haga doble clic en **Certificados de servidor**.</span><span class="sxs-lookup"><span data-stu-id="b8321-189">In **Internet Information Services (IIS) Manager**, click the local server node, and then in the center pane, double-click on **Server Certificates**.</span></span>  
  
2.  <span data-ttu-id="b8321-190">En el panel **Acciones** , haga clic en **Crear certificado autofirmado**.</span><span class="sxs-lookup"><span data-stu-id="b8321-190">In the **Actions** pane, click **Create Self-Signed Certificate**.</span></span>  
  
3.  <span data-ttu-id="b8321-191">En el cuadro de diálogo **Crear certificado autofirmado** , escriba un nombre para el certificado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-191">In the **Create Self-Signed Certificate** dialog box, enter a name for the certificate, and then click **OK**.</span></span>  
  
###### <a name="to-bind-a-certificate-to-a-web-site"></a><span data-ttu-id="b8321-192">Para enlazar un certificado a un sitio web</span><span class="sxs-lookup"><span data-stu-id="b8321-192">To bind a certificate to a Web site</span></span>  
  
1.  <span data-ttu-id="b8321-193">En el panel **Conexiones** , haga clic en **Sitio web predeterminado** (o el sitio de sincronización web, si es diferente del sitio web predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b8321-193">In the **Connections** pane, click the **Default Web Site** (or your Web synchronization site, if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="b8321-194">En el panel **Acciones** , haga clic en **Enlaces**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-194">In the **Actions** pane, click **Bindings**, and then click **Add**.</span></span> <span data-ttu-id="b8321-195">Se abre el cuadro de diálogo **Agregar enlace de sitio** .</span><span class="sxs-lookup"><span data-stu-id="b8321-195">The **Add Site Binding** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="b8321-196">En la lista desplegable **Tipo** , seleccione **https**.</span><span class="sxs-lookup"><span data-stu-id="b8321-196">From the **Type** drop-down list, select **https**.</span></span> <span data-ttu-id="b8321-197">Mantenga la configuración predeterminada en **Dirección IP** y **Puerto**.</span><span class="sxs-lookup"><span data-stu-id="b8321-197">Leave the default settings for **IP address** and **Port**.</span></span>  
  
4.  <span data-ttu-id="b8321-198">En la lista desplegable **Certificado SSL** , seleccione el certificado creado en "Para crear un certificado autofirmado para pruebas", haga clic en **Aceptar**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-198">From the **SSL certificate** drop-down list, select the certificate created in "To create a self-signed certificate for testing," click **OK**, and then click **Close**.</span></span>  
  
###### <a name="to-test-the-certificate"></a><span data-ttu-id="b8321-199">Para probar el certificado</span><span class="sxs-lookup"><span data-stu-id="b8321-199">To test the certificate</span></span>  
  
1.  <span data-ttu-id="b8321-200">En **Enternet Enformation Services (IIS) Manager**, haga clic en **Sitio web predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="b8321-200">In **Internet Information Services (IIS) Manager**, click **Default Web Site.**</span></span>  
  
2.  <span data-ttu-id="b8321-201">En el panel **Acciones**, haga clic en **Examinar \*:443(https)** .</span><span class="sxs-lookup"><span data-stu-id="b8321-201">From the **Actions** pane, click **Browse \*:443(https)**.</span></span>  
  
3.  <span data-ttu-id="b8321-202">Se abre Internet Explorer, con un mensaje que indica que "Hay un problema con el certificado de seguridad de este sitio web".</span><span class="sxs-lookup"><span data-stu-id="b8321-202">Internet Explorer will open and display a message that "There is a problem with this website's security certificate."</span></span> <span data-ttu-id="b8321-203">Esta advertencia indica que el certificado asociado no fue emitido por una entidad de certificación reconocida y podría no ser de confianza.</span><span class="sxs-lookup"><span data-stu-id="b8321-203">This warning tells you that the associated certificate was not issued by a recognized CA and might not be trustworthy.</span></span> <span data-ttu-id="b8321-204">Es una advertencia esperada, de modo que haga clic en **Pasar a este sitio web (no recomendado)** .</span><span class="sxs-lookup"><span data-stu-id="b8321-204">This is an expected warning, so click **Continue to this website (not recommended)**.</span></span>  
  
4.  <span data-ttu-id="b8321-205">Si se pide confirmación para **Conectar a localhost**, escriba un nombre de usuario y contraseña para continuar.</span><span class="sxs-lookup"><span data-stu-id="b8321-205">If you are prompted to **Connect to localhost**, enter a user name and password to proceed.</span></span> <span data-ttu-id="b8321-206">Debe aparecer la página predeterminada del sitio web.</span><span class="sxs-lookup"><span data-stu-id="b8321-206">You should see the default page for the Web site.</span></span>  
  
## <a name="setting-permissions-for-the-sql-server-replication-listener"></a><span data-ttu-id="b8321-207">Establecer los permisos para la Escucha de replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8321-207">Setting Permissions for the SQL Server Replication Listener</span></span>  
 <span data-ttu-id="b8321-208">Cuando un equipo suscriptor se conecta al equipo en el que se ejecuta IIS, se autentica usando el tipo de autenticación especificado al configurar IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-208">When a subscriber computer connects to the computer running IIS, the subscriber is authenticated by using the type of authentication specified when you configured IIS.</span></span> <span data-ttu-id="b8321-209">Tras autenticar al suscriptor, IIS comprueba si el suscriptor está autorizado para invocar la replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8321-209">After IIS authenticates the subscriber, IIS checks whether the subscriber is authorized to invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="b8321-210">Debe controlar los usuarios que pueden invocar la replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estableciendo permisos para replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="b8321-210">You control the users that can invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication by setting permissions for replisapi.dll.</span></span> <span data-ttu-id="b8321-211">Es necesario configurar permisos para impedir el acceso no autorizado a la replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8321-211">Properly configuring permissions is necessary to prevent unauthorized access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span>  
  
 <span data-ttu-id="b8321-212">Para configurar los permisos mínimos para la cuenta con la que se ejecuta la Escucha de replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , lleve a cabo el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b8321-212">To configure the minimum permissions for the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener runs, complete the following procedure.</span></span> <span data-ttu-id="b8321-213">Los pasos del siguiente procedimiento son únicamente para [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 con IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="b8321-213">The steps in the following procedure apply to [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 running IIS 7.0.</span></span>  
  
 <span data-ttu-id="b8321-214">Además de realizar los siguientes pasos, asegúrese de que los inicios de sesión necesarios se encuentran en la lista de acceso a la publicación (PAL).</span><span class="sxs-lookup"><span data-stu-id="b8321-214">In addition to performing the following steps, make sure that the required logins are in the publication access list (PAL).</span></span> <span data-ttu-id="b8321-215">Para obtener más información sobre la PAL, vea [Secure the Publisher](security/secure-the-publisher.md) (Proteger el publicador).</span><span class="sxs-lookup"><span data-stu-id="b8321-215">For more information about the PAL, see [Secure the Publisher](security/secure-the-publisher.md).</span></span>  
  
 <span data-ttu-id="b8321-216">**Importante** La cuenta creada en esta sección es la cuenta que se conectará al publicador y el distribuidor durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="b8321-216">**Important** The account created in this section is the account that will connect to the Publisher and Distributor during synchronization.</span></span> <span data-ttu-id="b8321-217">La cuenta se debe agregar como cuenta de inicio de sesión SQL en el servidor de distribución y publicación.</span><span class="sxs-lookup"><span data-stu-id="b8321-217">This account must be added as a SQL Login account on the distribution and publication server.</span></span>  
  
 <span data-ttu-id="b8321-218">La cuenta utilizada para la Escucha de replicación de SQL Server debe tener los permisos descritos en el tema sobre seguridad del agente de mezcla, en la sección sobre conexión al publicador o distribuidor.</span><span class="sxs-lookup"><span data-stu-id="b8321-218">The account used for the SQL Server Replication Listener must have permissions as described in the Merge Agent Security topic, in the "Connect to the Publisher or Distributor" section.</span></span>  
  
 <span data-ttu-id="b8321-219">En resumen, la cuenta debe:</span><span class="sxs-lookup"><span data-stu-id="b8321-219">In summary, the account must:</span></span>  
  
-   <span data-ttu-id="b8321-220">Ser miembro de la lista de acceso a la publicación (PAL).</span><span class="sxs-lookup"><span data-stu-id="b8321-220">Be a member of the Publication Access List (PAL).</span></span>  
  
-   <span data-ttu-id="b8321-221">Estar asignada un inicio de sesión asociado a un usuario en la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="b8321-221">Be mapped to a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="b8321-222">Estar asignada un inicio de sesión asociado a un usuario en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="b8321-222">Be mapped to a login associated with a user in the distribution database.</span></span>  
  
-   <span data-ttu-id="b8321-223">Tener permisos de lectura en el recurso compartido de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="b8321-223">Have Read permissions on the snapshot share.</span></span>  
  
#### <a name="to-configure-the-account-and-permissions"></a><span data-ttu-id="b8321-224">Para configurar la cuenta y los permisos</span><span class="sxs-lookup"><span data-stu-id="b8321-224">To configure the account and permissions</span></span>  
  
1.  <span data-ttu-id="b8321-225">Cree una cuenta local en el equipo en el que se ejecuta IIS:</span><span class="sxs-lookup"><span data-stu-id="b8321-225">Create a local account on the computer running IIS:</span></span>  
  
    1.  <span data-ttu-id="b8321-226">Abra el **Administrador del servidor**.</span><span class="sxs-lookup"><span data-stu-id="b8321-226">Open **Server Manager**.</span></span> <span data-ttu-id="b8321-227">En el menú Inicio, haga clic con el botón secundario en **Equipo**y, a continuación, en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-227">From the Start menu, right-click **Computer**, and then click **Manage**.</span></span>  
  
    2.  <span data-ttu-id="b8321-228">En el **Administrador del servidor**, expanda **Configuración**y, a continuación, expanda **Usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="b8321-228">In **Server Manager**, expand **Configuration**, and then expand **Local Users and Groups**.</span></span>  
  
    3.  <span data-ttu-id="b8321-229">Haga clic con el botón secundario en **Usuarios**y después en **Usuario nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b8321-229">Right-click **Users**, and then click **New User**.</span></span>  
  
    4.  <span data-ttu-id="b8321-230">Escriba un nombre de usuario y una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="b8321-230">Enter a user name and a strong password.</span></span> <span data-ttu-id="b8321-231">Desactive **El usuario debe cambiar la contraseña en el siguiente inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="b8321-231">Clear **User must change password at next logon**.</span></span>  
  
    5.  <span data-ttu-id="b8321-232">Haga clic en **Crear**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-232">Click **Create**, and then click **Close**.</span></span>  
  
2.  <span data-ttu-id="b8321-233">Agregue la cuenta al grupo IIS_IUSRS:</span><span class="sxs-lookup"><span data-stu-id="b8321-233">Add the account to the IIS_IUSRS group:</span></span>  
  
    1.  <span data-ttu-id="b8321-234">En el **Administrador del servidor**, expanda **Configuración**, expanda **Usuarios y grupos locales**y después haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="b8321-234">In **Server Manager**, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
    2.  <span data-ttu-id="b8321-235">Haga clic con el botón secundario en **IIS_IUSRS**y, después, en **Agregar a grupo**.</span><span class="sxs-lookup"><span data-stu-id="b8321-235">Right-click **IIS_IUSRS**, and then click **Add to Group**.</span></span>  
  
    3.  <span data-ttu-id="b8321-236">En el cuadro de diálogo **Propiedades de IIS_IUSRS** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-236">In the **IIS_IUSRS Properties** dialog box, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="b8321-237">En el cuadro de diálogo **Seleccionar usuarios, equipos o grupos** , agregue la cuenta que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="b8321-237">In the **Select Users, Computers, or Groups** dialog box, add the account created in step 1.</span></span>  
  
    5.  <span data-ttu-id="b8321-238">Compruebe que en **Desde esta ubicación** aparece el nombre del equipo local (no un dominio).</span><span class="sxs-lookup"><span data-stu-id="b8321-238">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="b8321-239">Si no aparece el nombre del equipo local, haga clic en **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-239">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="b8321-240">En el cuadro de diálogo **Ubicaciones** , seleccione el equipo local y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-240">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="b8321-241">Haga clic en **Aceptar** en los cuadros de diálogo **Seleccionar usuarios** , haga clic en**Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-241">In the **Select Users** dialog box and the **IIS_IUSRS Properties** dialog box, click**OK**.</span></span>  
  
3.  <span data-ttu-id="b8321-242">Conceda los permisos mínimos de cuenta en la carpeta que contiene el archivo replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="b8321-242">Grant minimum account permissions on the folder that contains replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="b8321-243">En el Explorador de Windows, haga clic con el botón secundario en la carpeta que ha creado para replisapi.dll y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b8321-243">In Windows Explorer, right-click the folder that you created for replisapi.dll, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="b8321-244">En la pestaña **Seguridad** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-244">On the **Security** tab, click **Edit**.</span></span>  
  
    3.  <span data-ttu-id="b8321-245">En el cuadro de diálogo **Permisos para \<foldername>** , haga clic en **Agregar** para agregar la cuenta que ha creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="b8321-245">In the **Permissions for \<foldername>** dialog box, click **Add** to add the account that you created in step 1.</span></span>  
  
    4.  <span data-ttu-id="b8321-246">Compruebe que en **Desde esta ubicación** aparece el nombre del equipo local (no un dominio).</span><span class="sxs-lookup"><span data-stu-id="b8321-246">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="b8321-247">Si no aparece el nombre del equipo local, haga clic en **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-247">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="b8321-248">En el cuadro de diálogo **Ubicaciones** , seleccione el equipo local y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-248">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="b8321-249">Compruebe que la cuenta solo tiene permisos de **Lectura**, **Lectura y ejecución** y **Mostrar el contenido de la carpeta**.</span><span class="sxs-lookup"><span data-stu-id="b8321-249">Verify that the account is granted only **Read**, **Read & Execute**, and **List Folder Contents** permissions.</span></span>  
  
    6.  <span data-ttu-id="b8321-250">Seleccione los usuarios o grupos que no requieran acceso al directorio , haga clic en **Quitar**y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-250">Select any users or groups that do not require access to the directory, click **Remove**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b8321-251">Cree un grupo de aplicaciones en **Administrador de Internet Information Services (IIS)** :</span><span class="sxs-lookup"><span data-stu-id="b8321-251">Create an application pool in **Internet Information Services (IIS) Manager**:</span></span>  
  
    1.  <span data-ttu-id="b8321-252">En **Administrador de Internet Information Services (IIS)** , en el panel **Conexiones** , expanda el nodo del servidor local.</span><span class="sxs-lookup"><span data-stu-id="b8321-252">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, expand the local server node.</span></span>  
  
    2.  <span data-ttu-id="b8321-253">Haga clic con el botón secundario en **Grupos de aplicaciones**y haga clic en **Grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-253">Right-click **Application Pools**, and then click **Add Application Pool**.</span></span>  
  
    3.  <span data-ttu-id="b8321-254">Escriba un nombre para el grupo de aplicaciones, deje los valores predeterminado para el resto de los campos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-254">Enter a name for the application pool, leave the default values for the remaining fields, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8321-255">Si piensa que va a tener más de dos clientes de sincronización simultáneos, podría crear hospedaje multiproceso en una única máquina.</span><span class="sxs-lookup"><span data-stu-id="b8321-255">If you anticipate having more than two concurrent synchronization clients, you might want to create a web garden.</span></span> <span data-ttu-id="b8321-256">Para obtener más información, consulte la sección Crear hospedaje multiproceso en una única máquina de [Configure Web Synchronization](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="b8321-256">For more information, see "Creating a Web Garden" in [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
5.  <span data-ttu-id="b8321-257">Asocie la cuenta al grupo de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="b8321-257">Associate the account with the application pool:</span></span>  
  
    1.  <span data-ttu-id="b8321-258">En **Administrador de Internet Information Services (IIS)** , expanda el nodo del servidor y, después, haga clic en **Grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-258">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on **Application Pools**.</span></span>  
  
    2.  <span data-ttu-id="b8321-259">Haga clic con el botón secundario en el grupo de aplicaciones que ha creado y, a continuación, haga clic en **Establecer valores predeterminados de grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-259">Right-click the application pool that you created, and then click **Set Application Pool Defaults**.</span></span>  
  
    3.  <span data-ttu-id="b8321-260">En el cuadro de diálogo **Valores predeterminados de grupo de aplicaciones** , desplácese a la sección **Procesar modelo** y, a continuación, haga clic en el campo **Identidad** .</span><span class="sxs-lookup"><span data-stu-id="b8321-260">In the **Application Pool Defaults** dialog box, scroll down to the **Process Model** section, and then click the **Identity** field.</span></span>  
  
    4.  <span data-ttu-id="b8321-261">Haga clic en el botón de puntos suspensivos que hay en el lado derecho de la fila **Identidad** .</span><span class="sxs-lookup"><span data-stu-id="b8321-261">Click the ellipsis button on the right side of the **Identity** row.</span></span>  
  
    5.  <span data-ttu-id="b8321-262">Haga clic en el botón de radio **Cuenta personalizada** y, a continuación, en **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="b8321-262">Click the **Custom Account** radio button, and then click **Set**.</span></span>  
  
    6.  <span data-ttu-id="b8321-263">En los campos **Nombre de usuario** y **Contraseña** , escriba la cuenta y la contraseña que creó en el paso 1 y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-263">In the **User name** and **Password** fields, enter the account and password that were created in step 1, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="b8321-264">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Identidad de grupo de aplicaciones** y, a continuación, de nuevo en **Aceptar** para cerrar el cuadro de diálogo **Valores predeterminados de grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-264">Click **OK** to close the **Application Pool Identity** dialog box, and then click **OK** again to close the **Application Pool Defaults**dialog box.</span></span>  
  
6.  <span data-ttu-id="b8321-265">Asocie el grupo de aplicaciones al sitio web de replicación:</span><span class="sxs-lookup"><span data-stu-id="b8321-265">Associate the application pool with the replication Web site:</span></span>  
  
    1.  <span data-ttu-id="b8321-266">En el **Administrador de Internet Information Services (IIS)** , expanda el nodo de servidor local y, a continuación, haga clic en **Sitio web predeterminado** (o el sitio de sincronización web si es diferente del sitio web predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b8321-266">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
    2.  <span data-ttu-id="b8321-267">En el panel **Acciones** , en **Administrar sitio web**, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="b8321-267">In the **Actions** pane, under **Manage Web Site**, click **Advanced Settings**.</span></span>  
  
    3.  <span data-ttu-id="b8321-268">En el cuadro de diálogo **Configuración avanzada** , haga clic en el botón de puntos suspensivos que hay a la derecha de **Grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8321-268">In the **Advanced Settings** dialog box, click on the ellipsis button to the right of **Application Pool**.</span></span>  
  
    4.  <span data-ttu-id="b8321-269">En la lista desplegable **Grupo de aplicaciones** , seleccione el grupo de aplicaciones que ha creado en el paso 4 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-269">From the **Application pool** drop-down list, select the application pool you created in step 4, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="b8321-270">Vuelva a hacer clic en **Aceptar** para cerrar Configuración avanzada.</span><span class="sxs-lookup"><span data-stu-id="b8321-270">Click **OK** again to close Advanced Settings.</span></span>  
  
## <a name="testing-the-connection-to-replisapidll"></a><span data-ttu-id="b8321-271">Probar la conexión con replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="b8321-271">Testing the Connection to replisapi.dll</span></span>  
 <span data-ttu-id="b8321-272">Ejecute la sincronización web en modo de diagnóstico para probar la conexión al equipo en el que se ejecuta IIS y para asegurarse de que el certificado SSL (Capa de sockets seguros) está instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8321-272">Run Web synchronization in diagnostic mode to test the connection to the computer running IIS and to make sure that the Secure Sockets Layer (SSL) certificate is properly installed.</span></span> <span data-ttu-id="b8321-273">Para ejecutar la sincronización web en modo de diagnóstico, debe ser administrador en el equipo donde se ejecuta IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-273">To run Web synchronization in diagnostic mode, you must be an administrator on the computer running IIS.</span></span>  
  
#### <a name="to-test-the-connection-to-replisapidll"></a><span data-ttu-id="b8321-274">Para probar la conexión con replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="b8321-274">To test the connection to replisapi.dll</span></span>  
  
1.  <span data-ttu-id="b8321-275">Asegúrese de que la configuración de red de área local (LAN) del suscriptor es correcta:</span><span class="sxs-lookup"><span data-stu-id="b8321-275">Make sure that local area network (LAN) settings at the Subscriber are correct:</span></span>  
  
    1.  <span data-ttu-id="b8321-276">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, en el menú **Herramientas** , haga clic en **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="b8321-276">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
    2.  <span data-ttu-id="b8321-277">En la pestaña **Conexiones** , haga clic en **Configuración de LAN**.</span><span class="sxs-lookup"><span data-stu-id="b8321-277">On the **Connections** tab, click **LAN Settings**.</span></span>  
  
    3.  <span data-ttu-id="b8321-278">Si no se utiliza ningún servidor proxy en la configuración de red de área local (LAN), desactive las casillas **Detectar la configuración automáticamente** y **Utilizar un servidor proxy para su LAN**.</span><span class="sxs-lookup"><span data-stu-id="b8321-278">If a proxy server is not used on the LAN, clear **Automatically Detect Settings** and **Use a proxy server for your LAN**.</span></span>  
  
    4.  <span data-ttu-id="b8321-279">Si se utiliza un servidor proxy, haga clic en **Utilizar un servidor proxy para su LAN** y **No usar servidor proxy para direcciones locales**y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-279">If a proxy server is used, click **Use a proxy server for your LAN** and **Bypass proxy server for local addresses**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b8321-280">En el suscriptor, en Internet Explorer, conéctese al servidor en modo de diagnóstico agregando `?diag` a la dirección de replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="b8321-280">At the Subscriber, in Internet Explorer, connect to the server in diagnostic mode by appending `?diag` to the address for the replisapi.dll.</span></span> <span data-ttu-id="b8321-281">Por ejemplo: `https://server.domain.com/directory/replisapi.dll?diag`.</span><span class="sxs-lookup"><span data-stu-id="b8321-281">For example: `https://server.domain.com/directory/replisapi.dll?diag`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8321-282">En el ejemplo anterior, **servidor.dominio.com** se debe reemplazar con el nombre de **Emitido** exacto que aparece en la sección **Certificados de servidor** en el Administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-282">In the example above, **server.domain.com** should be replaced with the exact **Issued To** name listed under the **Server Certificates** section in IIS Manager.</span></span>  
  
3.  <span data-ttu-id="b8321-283">Si el sistema operativo Windows no reconoce el certificado especificado para IIS, aparece el cuadro de diálogo **Alerta de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="b8321-283">If the certificate that you specified for IIS is not recognized by the Windows operating system, the **Security Alert** dialog box appears.</span></span> <span data-ttu-id="b8321-284">Esta alerta puede producirse porque el certificado es un certificado de prueba, o bien porque lo emitió una entidad de certificación (CA) que Windows no reconoce.</span><span class="sxs-lookup"><span data-stu-id="b8321-284">This alert might occur because the certificate is a test certificate or the certificate was issued by a certification authority (CA) that Windows does not recognize.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8321-285">Si este cuadro de diálogo no aparece, asegúrese de que el certificado del servidor al que está obteniendo acceso se ha agregado al almacén de certificados del suscriptor como certificado de confianza.</span><span class="sxs-lookup"><span data-stu-id="b8321-285">If this dialog box does not appear, make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="b8321-286">Para obtener más información acerca de la exportación de certificados, vea la documentación de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-286">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
    1.  <span data-ttu-id="b8321-287">En el cuadro de diálogo **Alerta de seguridad** , haga clic en **Ver certificado**.</span><span class="sxs-lookup"><span data-stu-id="b8321-287">In the **Security Alert** dialog box, click **View Certificate**.</span></span>  
  
    2.  <span data-ttu-id="b8321-288">En el cuadro de diálogo **Certificado** de la pestaña **General** , haga clic en **Instalar certificado**.</span><span class="sxs-lookup"><span data-stu-id="b8321-288">In the **Certificate** dialog box, on the **General** tab, click **Install Certificate**.</span></span>  
  
    3.  <span data-ttu-id="b8321-289">Complete el Asistente para importación de certificados, aceptando los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b8321-289">Complete the Certificate Import Wizard, accepting the defaults.</span></span>  
  
    4.  <span data-ttu-id="b8321-290">En el cuadro de diálogo **Advertencia de seguridad** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b8321-290">In the **Security Warning** dialog box, click **Yes**.</span></span>  
  
    5.  <span data-ttu-id="b8321-291">En el cuadro de diálogo de confirmación del Asistente para importación de certificados, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8321-291">In the Certificate Import Wizard confirmation dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="b8321-292">Cierre el cuadro de diálogo **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="b8321-292">Close the **Certificate** dialog box.</span></span>  
  
    7.  <span data-ttu-id="b8321-293">En el cuadro de diálogo **Alerta de seguridad** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b8321-293">In the **Security Alert** dialog box, click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8321-294">Los certificados los instalan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8321-294">Certificates are installed for users.</span></span> <span data-ttu-id="b8321-295">Este proceso lo deben realizar todos los usuarios que vayan a realizar sincronizaciones con IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-295">This process must be performed for each user that will synchronize with IIS.</span></span>  
  
4.  <span data-ttu-id="b8321-296">En el cuadro de diálogo **Conectar con \<ServerName>** , especifique el nombre de inicio de sesión y la contraseña que utilizará el Agente de mezcla para conectarse a IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-296">In the **Connect to \<ServerName>** dialog box, specify the login and password that the Merge Agent will use to connect to IIS.</span></span> <span data-ttu-id="b8321-297">Estas credenciales también se especificarán en el Asistente para nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8321-297">These credentials will also be specified in the New Subscription Wizard.</span></span>  
  
5.  <span data-ttu-id="b8321-298">En la ventana de Internet Explorer con **información de diagnóstico sobre la sincronización web de SQL**, compruebe que el valor de todas las columnas de **estado** de la página sea **SUCCESS**.</span><span class="sxs-lookup"><span data-stu-id="b8321-298">In the Internet Explorer window called **SQL Websync diagnostic information**, verify that the value in each **Status** column on the page is **SUCCESS**.</span></span>  
  
6.  <span data-ttu-id="b8321-299">Compruebe que el certificado se haya instalado correctamente en el suscriptor:</span><span class="sxs-lookup"><span data-stu-id="b8321-299">Make sure that the certificate is installed correctly on the Subscriber:</span></span>  
  
    1.  <span data-ttu-id="b8321-300">Cierre y vuelva a abrir Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b8321-300">Close and then reopen Internet Explorer.</span></span>  
  
    2.  <span data-ttu-id="b8321-301">Conéctese al servidor en modo de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="b8321-301">Connect to the server in diagnostic mode.</span></span> <span data-ttu-id="b8321-302">Si el certificado se ha instalado correctamente, no aparecerá el cuadro de diálogo **Alerta de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="b8321-302">If the certificate is installed properly, the **Security Alert** dialog box will not appear.</span></span> <span data-ttu-id="b8321-303">Si se muestra este cuadro de diálogo, se producirá un error en el Agente de mezcla cuando intente conectarse al equipo en el que se ejecuta IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-303">If the dialog box appears, the Merge Agent will fail when it tries to connect to the computer that is running IIS.</span></span> <span data-ttu-id="b8321-304">Debe asegurarse de que el certificado del servidor al que está obteniendo acceso se ha agregado al almacén de certificados del suscriptor como certificado de confianza.</span><span class="sxs-lookup"><span data-stu-id="b8321-304">You must make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="b8321-305">Para obtener más información acerca de la exportación de certificados, vea la documentación de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8321-305">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8321-306">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8321-306">See Also</span></span>  
 <span data-ttu-id="b8321-307">[Sincronización web para la replicación de mezcla](web-synchronization-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="b8321-307">[Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="b8321-308">Configurar la sincronización web</span><span class="sxs-lookup"><span data-stu-id="b8321-308">Configure Web Synchronization</span></span>](configure-web-synchronization.md)  
  
  
