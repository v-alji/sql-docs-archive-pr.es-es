---
title: Copias de seguridad y restauración Reporting Services aplicaciones de servicio de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dfb4ed77-90e5-4273-b690-89a945508ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488659d269542381be9bcf1b1b6115acf89f8a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672809"
---
# <a name="backup-and-restore-reporting-services-sharepoint-service-applications"></a><span data-ttu-id="262ea-102">Copias de seguridad y restauración de aplicaciones de servicio de SharePoint para Reporting Services</span><span class="sxs-lookup"><span data-stu-id="262ea-102">Backup and Restore Reporting Services SharePoint Service Applications</span></span>
  <span data-ttu-id="262ea-103">Este tema se describe cómo hacer una copia de seguridad y restaurar una aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] mediante Administración central de SharePoint o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="262ea-103">This topic describes how to backup and restore a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services application using SharePoint Central Administration or PowerShell.</span></span> <span data-ttu-id="262ea-104">El tema contiene:</span><span class="sxs-lookup"><span data-stu-id="262ea-104">The topic contains:</span></span>  
  
-   [<span data-ttu-id="262ea-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="262ea-105">Limitations and Restrictions</span></span>](#bkmk_Restrictions)  
  
-   [<span data-ttu-id="262ea-106">Copia de seguridad de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="262ea-106">Backup The Service application</span></span>](#bkmk_backup)  
  
-   [<span data-ttu-id="262ea-107">Restauración de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="262ea-107">Restore the Service Application</span></span>](#bkmk_restore)  
  
##  <a name="before-you-begin"></a><a name="bkmk_BeforeYouBegin"></a> <span data-ttu-id="262ea-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="262ea-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="bkmk_Restrictions"></a> <span data-ttu-id="262ea-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="262ea-109">Limitations and Restrictions</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="262ea-110">Se puede realizar una copia de seguridad y una restauración parciales de aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] mediante la funcionalidad de copia de seguridad y restauración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="262ea-110">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications can partially be backed up and restored using the SharePoint backup and restore functionality.</span></span> <span data-ttu-id="262ea-111">**Se requieren pasos adicionales** y los pasos se documentan en este tema.</span><span class="sxs-lookup"><span data-stu-id="262ea-111">**Additional steps are required** and the steps are documented in this topic.</span></span> <span data-ttu-id="262ea-112">Actualmente, el proceso de copia de seguridad **no** realiza una copia de seguridad de las claves de cifrado ni de las credenciales para las cuentas de ejecución desatendidas (UEA) o con autenticación de Windows en la base de datos de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="262ea-112">Currently the backup process **does not** backup encryption keys and credentials for unattended execution accounts (UEA) or windows authentication to the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] database.</span></span>  
  
###  <a name="recommendations"></a><a name="bkmk_recommendations"></a> <span data-ttu-id="262ea-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="262ea-113">Recommendations</span></span>  
  
-   <span data-ttu-id="262ea-114">Realice una copia de seguridad de las claves de cifrado antes de iniciar la copia de seguridad de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="262ea-114">Backup the encryption keys before starting the SharePoint backup.</span></span> <span data-ttu-id="262ea-115">Si no hace una copia de seguridad de las claves de cifrado, no podrá acceder a los datos cifrados después de restaurar la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="262ea-115">If you do not backup the encryption keys, then you will not be able to access your encrypted data, following the restore of the service application.</span></span> <span data-ttu-id="262ea-116">Tendrá que eliminar los datos cifrados.</span><span class="sxs-lookup"><span data-stu-id="262ea-116">You will need to delete your encrypted data.</span></span>  
  
-   <span data-ttu-id="262ea-117">Compruebe si la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] utiliza UEA o la autenticación de Windows para acceder a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="262ea-117">Verify if your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application is using UEA or Windows authentication for database access.</span></span> <span data-ttu-id="262ea-118">Si es así, compruebe cuáles son las credenciales correctas para poder configurar correctamente la aplicación de servicio después del proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="262ea-118">If it is using either, verify what the proper credentials are so you can correctly configure the service application after the restore process.</span></span>  
  
-   <span data-ttu-id="262ea-119">Compruebe que el archivo de registro de copia de seguridad de SharePoint se crea en la misma carpeta que el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="262ea-119">Review the SharePoint backup log is created in the same folder as the backup file.</span></span> <span data-ttu-id="262ea-120">El archivo se denomina normalmente **spbackup.log**</span><span class="sxs-lookup"><span data-stu-id="262ea-120">The file is typically named **spbackup.log**</span></span>  
  
##  <a name="backup-the-service-application"></a><a name="bkmk_backup"></a><span data-ttu-id="262ea-121">Copia de seguridad de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="262ea-121">Backup The Service application</span></span>  
 <span data-ttu-id="262ea-122">Realice los pasos siguientes en el orden indicado:</span><span class="sxs-lookup"><span data-stu-id="262ea-122">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="262ea-123">Realice una copia de seguridad de las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="262ea-123">Backup the encryption keys</span></span>  
  
2.  <span data-ttu-id="262ea-124">Copia de seguridad de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="262ea-124">Backup the Service application</span></span>  
  
3.  <span data-ttu-id="262ea-125">Compruebe si la aplicación de servicio utiliza UEA o la autenticación de Windows para acceder a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="262ea-125">Verify if you service application uses an UEA or Windows authentication for database access.</span></span> <span data-ttu-id="262ea-126">Si es así, anote las credenciales para poder usarlas cuando configure la aplicación de servicio una vez restaurada.</span><span class="sxs-lookup"><span data-stu-id="262ea-126">If it does, make a note of the credentials so you can use them to configure the service application after it is restored.</span></span>  
  
### <a name="backup-the-encryption-keys-using-central-administration"></a><span data-ttu-id="262ea-127">Copia de seguridad de las claves de cifrado mediante Administración central</span><span class="sxs-lookup"><span data-stu-id="262ea-127">Backup the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="262ea-128">Para obtener más información sobre cómo realizar copias de seguridad de las claves de cifrado de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vea la sección "Claves de cifrado" de [Administrar una aplicación de servicio de SharePoint para Reporting Services](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="262ea-128">For information on backing up the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
###  <a name="backup-the-service-application-using-sharepoint-central-administration"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="262ea-129">Copia de seguridad de la aplicación de servicio mediante administración central de SharePoint</span><span class="sxs-lookup"><span data-stu-id="262ea-129">Backup the Service application Using SharePoint Central Administration</span></span>  
 <span data-ttu-id="262ea-130">Para realizar una copia de seguridad de la aplicación de servicio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="262ea-130">To back up the Service Application, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="262ea-131">En Administración central de SharePoint, haga clic en **Realizar una copia de seguridad** en el grupo **Realizar copias de seguridad y restauración**.</span><span class="sxs-lookup"><span data-stu-id="262ea-131">In SharePoint Central Administration Click **Perform a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="262ea-132">En el nodo **Servicios compartidos** , expanda **Aplicaciones de servicios compartidos** y seleccione la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="262ea-132">Under the **Shared Services** node, expand **Shared Service Applications** and select your service application.</span></span> <span data-ttu-id="262ea-133">Tendrá un tipo de **Aplicación del servicio SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="262ea-133">It will have a type of **SQL Server Reporting Services Service Application**.</span></span>  
  
3.  <span data-ttu-id="262ea-134">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="262ea-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="262ea-135">Escriba la ruta de acceso en **Ubicación de copia de seguridad:** y haga clic en **Iniciar copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="262ea-135">Type the path for the **Backup location:** and click **Start Backup**</span></span>  
  
5.  <span data-ttu-id="262ea-136">Repita el proceso anterior, pero en lugar de seleccionar la aplicación de servicio, expanda el nodo **Servidores proxy de servicios compartidos** y seleccione el proxy de la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="262ea-136">Repeat the process above but instead of selecting the service application, expand the **Shared Services Proxies** node, and select service application proxy.</span></span> <span data-ttu-id="262ea-137">Tendrá un tipo de **Proxy de aplicación del servicio SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="262ea-137">It will have a type of **SQL Server Reporting Services Service Application Proxy**.</span></span>  
  
 <span data-ttu-id="262ea-138">Para obtener más información, consulte los siguientes temas en la documentación de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="262ea-138">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="262ea-139">[Copia de seguridad de una aplicación de servicio (SharePoint Foundation 2010) en la documentación de SharePoint](https://msdn.microsoft.com/library/ee748601.aspx).</span><span class="sxs-lookup"><span data-stu-id="262ea-139">[Back up a service application (SharePoint Foundation 2010) in the SharePoint documenttation](https://msdn.microsoft.com/library/ee748601.aspx).</span></span>  
  
 [<span data-ttu-id="262ea-140">Copia de seguridad de una aplicación de servicio (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="262ea-140">Back up a service application (SharePoint Server 2010)</span></span>](https://technet.microsoft.com/library/ee428318.aspx)  
  
### <a name="verify-execution-account-and-database-authentication"></a><span data-ttu-id="262ea-141">Comprobación de la cuenta de ejecución y autenticación de la base de datos</span><span class="sxs-lookup"><span data-stu-id="262ea-141">Verify Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="262ea-142">**Cuenta de la ejecución:** para comprobar si la aplicación de servicio utiliza una cuenta de ejecución:</span><span class="sxs-lookup"><span data-stu-id="262ea-142">**Execution Account:** To verify if your service application is using an execution account:</span></span>  
  
1.  <span data-ttu-id="262ea-143">En administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio** en el grupo **Administración de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="262ea-143">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="262ea-144">Haga clic en el nombre de la aplicación de servicio y, a continuación, haga clic en **administrar** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="262ea-144">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="262ea-145">Haga clic en **Cuenta de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="262ea-145">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="262ea-146">Si se configura una cuenta de ejecución, tendrá que conocer las credenciales cuando llegue el momento de restaurar una copia de seguridad de la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="262ea-146">If an execution account is configured, you need to know the credentials when it is time to restore the service application backup.</span></span> <span data-ttu-id="262ea-147">No realice el procedimiento de copia de seguridad y restauración hasta que sepa cuáles son las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="262ea-147">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
 <span data-ttu-id="262ea-148">**Autenticación de la base de datos:** para comprobar si la aplicación de servicio utiliza la Autenticación de Windows para la autenticación de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="262ea-148">**Database Authentication:** To verify if your service application is using Windows Authentication for the database authentication:</span></span>  
  
1.  <span data-ttu-id="262ea-149">En administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio** en el grupo **Administración de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="262ea-149">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="262ea-150">Haga clic el nombre de la aplicación de servicio y después en **Propiedades** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="262ea-150">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="262ea-151">Examine la sección **Base de datos del servicio Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="262ea-151">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="262ea-152">Si se configura la autenticación de Windows, necesita conocer las credenciales para poder configurar la aplicación de servicio una vez restaurada.</span><span class="sxs-lookup"><span data-stu-id="262ea-152">If Windows Authentication is configured, you need to know the credentials so you can configure the service application after you restore it.</span></span> <span data-ttu-id="262ea-153">No realice el procedimiento de copia de seguridad y restauración hasta que sepa cuáles son las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="262ea-153">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
##  <a name="restore-the-service-application"></a><a name="bkmk_restore"></a><span data-ttu-id="262ea-154">Restauración de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="262ea-154">Restore the Service Application</span></span>  
 <span data-ttu-id="262ea-155">Realice los pasos siguientes en el orden indicado:</span><span class="sxs-lookup"><span data-stu-id="262ea-155">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="262ea-156">Restaure la aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="262ea-156">Restore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="262ea-157">Restaure las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="262ea-157">Restore the encryption keys</span></span>  
  
3.  <span data-ttu-id="262ea-158">Si la aplicación de servicio utilizaba una cuenta de ejecución o la autenticación de Windows para el acceso a la base de datos, configure las credenciales.</span><span class="sxs-lookup"><span data-stu-id="262ea-158">If your service application was using an execution account or Windows authentication for database access, configure the credentials.</span></span>  
  
### <a name="restore-the-service-application-using-sharepoint-central-administration"></a><span data-ttu-id="262ea-159">Restauración de la aplicación de servicio mediante Administración central de SharePoint</span><span class="sxs-lookup"><span data-stu-id="262ea-159">Restore the Service application Using SharePoint Central Administration</span></span>  
  
1.  <span data-ttu-id="262ea-160">En Administración central de SharePoint, haga clic en **Restaurar de una copia de seguridad** en el grupo **Realizar copias de seguridad y restauración**.</span><span class="sxs-lookup"><span data-stu-id="262ea-160">In SharePoint Central Administration Click **Restore from a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="262ea-161">Especifique la ruta de acceso del archivo de copia de seguridad en **Ubicación del directorio de copia de seguridad** y haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="262ea-161">Type the path to your backup file in **Backup Directory Location** box and click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="262ea-162">Seleccione la copia de seguridad de la aplicación de servicio en la lista **Componente principal** y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="262ea-162">Select your service application backup from the **Top Component** list and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="262ea-163">Seleccione la aplicación de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="262ea-163">Select your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="262ea-164">En la sección **Nombres y contraseñas de inicio de sesión** , escriba la contraseña del nombre de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="262ea-164">In the **Login Names and Passwords** section type the password for the login name.</span></span> <span data-ttu-id="262ea-165">El cuadro de nombre de inicio de sesión debe rellenarse con el inicio de sesión que usaba la aplicación de servicio antes de que se realizara la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="262ea-165">The login name box should be populated with the login the service application was using prior to the backup.</span></span>  
  
6.  <span data-ttu-id="262ea-166">Haga clic en **Iniciar restauración**.</span><span class="sxs-lookup"><span data-stu-id="262ea-166">Click **Start Restore**.</span></span>  
  
7.  <span data-ttu-id="262ea-167">Repita el proceso anterior, pero en lugar de restaurar la aplicación de servicio, expanda el nodo **Servicios compartidos** y después expanda el nodo **Aplicaciones de servicios compartidos** .</span><span class="sxs-lookup"><span data-stu-id="262ea-167">Repeat the process above but instead of restoring the service application, expand the **Shared Services** node and then expand the **Shared Service Applications** node.</span></span>  
  
 <span data-ttu-id="262ea-168">Para obtener más información, consulte los siguientes temas en la documentación de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="262ea-168">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="262ea-169">[Restauración de una aplicación de servicio (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span><span class="sxs-lookup"><span data-stu-id="262ea-169">[Restore a service application (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span></span>  
  
 <span data-ttu-id="262ea-170">[Restauración de una aplicación de servicio (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span><span class="sxs-lookup"><span data-stu-id="262ea-170">[Restore a service application (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span></span>  
  
### <a name="restore-the-encryption-keys-using-central-administration"></a><span data-ttu-id="262ea-171">Restauración de las claves de cifrado mediante Administración central</span><span class="sxs-lookup"><span data-stu-id="262ea-171">Restore the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="262ea-172">Para obtener más información sobre la restauración de las claves de cifrado de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vea la sección "Claves de cifrado" de [Administrar una aplicación de servicio de SharePoint para Reporting Services](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="262ea-172">For information on restoring the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
### <a name="configure-the-execution-account-and-database-authentication"></a><span data-ttu-id="262ea-173">Configurar la cuenta de ejecución y la autenticación de la base de datos</span><span class="sxs-lookup"><span data-stu-id="262ea-173">Configure the Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="262ea-174">**Cuenta de ejecución:** si la aplicación de servicio utilizaba una cuenta de ejecución, realice el procedimiento siguiente para configurarla:</span><span class="sxs-lookup"><span data-stu-id="262ea-174">**Execution Account:** If your service application was using an execution account complete the following steps to configure it:</span></span>  
  
1.  <span data-ttu-id="262ea-175">En administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio** en el grupo **Administración de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="262ea-175">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="262ea-176">Haga clic en el nombre de la aplicación de servicio y, a continuación, haga clic en **administrar** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="262ea-176">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="262ea-177">Haga clic en **Cuenta de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="262ea-177">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="262ea-178">Especifique la cuenta, la contraseña y active la casilla **Especificar una cuenta de ejecución** .</span><span class="sxs-lookup"><span data-stu-id="262ea-178">Type the account, password, and select the **Specify and Execution Account** box.</span></span>  
  
5.  <span data-ttu-id="262ea-179">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="262ea-179">Click **OK**.</span></span>  
  
 <span data-ttu-id="262ea-180">**Autenticación de la base de datos:** si la aplicación de servicio utilizaba la autenticación de Windows para la autenticación de la base de datos, realice el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="262ea-180">**Database Authentication:** If your service application was using Windows Authentication for the database authentication complete the following steps:</span></span>  
  
1.  <span data-ttu-id="262ea-181">En administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio** en el grupo **Administración de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="262ea-181">In SharePoint Central Administration click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="262ea-182">Haga clic el nombre de la aplicación de servicio y después en **Propiedades** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="262ea-182">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="262ea-183">Examine la sección **Base de datos del servicio Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="262ea-183">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="262ea-184">Seleccione **Autenticación de Windows**.</span><span class="sxs-lookup"><span data-stu-id="262ea-184">Select **Windows Authentication**.</span></span>  
  
5.  <span data-ttu-id="262ea-185">Escriba la cuenta y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="262ea-185">Type the account and password.</span></span> <span data-ttu-id="262ea-186">Seleccione **Usar como credenciales de Windows** si procede.</span><span class="sxs-lookup"><span data-stu-id="262ea-186">Select **Use as Windows Credentials** if appropriate.</span></span>  
  
6.  <span data-ttu-id="262ea-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="262ea-187">Click **Ok**</span></span>  
  
  
