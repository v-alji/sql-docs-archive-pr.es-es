---
title: Actualizar credenciales en orígenes de datos de informe desde un sitio de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e0c50b6e-89e7-4b4d-8fe5-c90682c5d1b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 923fee5656ed6032201fb4276fcca75be799e42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662575"
---
# <a name="update-credentials-in-report-data-sources-from-a-sharepoint-site"></a><span data-ttu-id="de7ea-102">Actualizar credenciales en orígenes de datos de informe desde un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="de7ea-102">Update Credentials in Report Data Sources from a SharePoint Site</span></span>
  <span data-ttu-id="de7ea-103">En este tema se describe cómo actualizar los orígenes de datos incrustados en informes y los orígenes de datos compartidos en una biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de7ea-103">This topic describes how to update data sources embedded in reports and shared data sources that are saved in a SharePoint document library.</span></span>  
  
 <span data-ttu-id="de7ea-104">Muchos de sus informes pueden incluir orígenes de datos o utilizar orígenes de datos compartidos configurados para usar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="de7ea-104">Many of your reports might include data sources or use shared data sources that are configured to use Windows Authentication.</span></span> <span data-ttu-id="de7ea-105">En algunas circunstancias, como cuando crea alertas de datos para informes guardados en una biblioteca de documentos de SharePoint, tendrá que actualizar las credenciales del origen de datos a las credenciales almacenadas o no requerir ninguna credencial.</span><span class="sxs-lookup"><span data-stu-id="de7ea-105">Under some circumstances, such as creating data alerts on reports saved to a SharePoint document library, you need to update the data source credentials to stored credentials or require no credentials.</span></span>  
  
 <span data-ttu-id="de7ea-106">Para utilizar credenciales almacenadas en informes, puede decidir crear y usar un nuevo inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de7ea-106">To use stored credentials in reports, you might decide to create and use a new SQL Server login.</span></span> <span data-ttu-id="de7ea-107">Para obtener más información, vea [Crear un inicio de sesión](../../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="de7ea-107">For more information, see [Create a Login](../../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
### <a name="to-update-an-embedded-data-source-to-use-stored-credentials"></a><span data-ttu-id="de7ea-108">Para actualizar un origen de datos incrustado de modo que use credenciales almacenadas</span><span class="sxs-lookup"><span data-stu-id="de7ea-108">To update an embedded data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="de7ea-109">Vaya a la biblioteca de documentos de SharePoint donde guardó el informe.</span><span class="sxs-lookup"><span data-stu-id="de7ea-109">Go to the SharePoint document library where you saved the report.</span></span>  
  
2.  <span data-ttu-id="de7ea-110">Haga clic en el icono para expandir el menú desplegable del informe y, después, haga clic en **Administrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-110">Click the icon for the expand drop-down menu on the report and then click **Manage Data Sources**.</span></span>  
  
     <span data-ttu-id="de7ea-111">Se abre la página Administrar orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="de7ea-111">The Manage Data Sources page opens.</span></span>  
  
3.  <span data-ttu-id="de7ea-112">En la columna **Nombre** , haga clic en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="de7ea-112">In the **Name** column, click the data source.</span></span>  
  
4.  <span data-ttu-id="de7ea-113">Para **Tipo de conexión** , compruebe que la opción **Origen de datos personalizado** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de7ea-113">For **Connection Type** verify that the **Custom data source** option is selected.</span></span>  
  
     <span data-ttu-id="de7ea-114">Esta opción indica que el origen de datos está incrustado en el informe.</span><span class="sxs-lookup"><span data-stu-id="de7ea-114">This option indicates that the data source is embedded in the report.</span></span>  
  
5.  <span data-ttu-id="de7ea-115">Deje las opciones **Tipo de origen de datos** y **Cadena de conexión** tal como están, a menos que desee que el informe se conecte a un tipo diferente de origen de datos, a un servidor diferente o a un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="de7ea-115">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the report to connect to different type of data source, a different server, or data store.</span></span>  
  
6.  <span data-ttu-id="de7ea-116">Para **Credenciales**, seleccione **Credenciales almacenadas**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-116">For **Credentials**, select **Stored credentials**.</span></span> <span data-ttu-id="de7ea-117">Esta opción solo funciona si el origen de datos no acepta credenciales o si se pasan credenciales de otra manera.</span><span class="sxs-lookup"><span data-stu-id="de7ea-117">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="de7ea-118">En algunas circunstancias se puede usar también la opción **No se necesitan credenciales** .</span><span class="sxs-lookup"><span data-stu-id="de7ea-118">The **Credentials are not required** option can also be used under some circumstances.</span></span>  
  
     <span data-ttu-id="de7ea-119">En algunos tipos de orígenes de datos, se debe configurar una cuenta de ejecución desatendida en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="de7ea-119">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="de7ea-120">Para más información, vea el tema del tipo de origen de datos correspondiente en [Agregar datos de orígenes de datos externos &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) y [Configurar la cuenta de ejecución desatendida &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="de7ea-120">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
7.  <span data-ttu-id="de7ea-121">Escriba un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="de7ea-121">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="de7ea-122">Si la cuenta es una cuenta de usuario de dominio de Windows, especifíquelo con este formato: \<domain> \\<cuenta \> y, a continuación, seleccione **usar como credenciales de Windows para la conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-122">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source**.</span></span>  
  
    -   <span data-ttu-id="de7ea-123">Si el nombre de usuario y la contraseña son credenciales de la base de datos, no seleccione **Utilizar como credenciales de Windows para la conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-123">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="de7ea-124">Si el servidor de base de datos admite la suplantación o la delegación, puede seleccionar **Establecer contexto de ejecución en esta cuenta**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-124">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
8.  <span data-ttu-id="de7ea-125">Para comprobar que el origen de datos se puede conectar usando las credenciales actualizadas, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-125">To verify the data source can connect by using the updated credentials, click **Test connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-update-a-shared-data-source-to-use-stored-credentials"></a><span data-ttu-id="de7ea-126">Para actualizar un origen de datos compartido de modo que use credenciales almacenadas</span><span class="sxs-lookup"><span data-stu-id="de7ea-126">To update a shared data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="de7ea-127">Vaya a la biblioteca de documentos de SharePoint donde guardó el origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="de7ea-127">Go to the SharePoint document library where you saved the shared data source.</span></span>  
  
2.  <span data-ttu-id="de7ea-128">Haga clic en el icono para expandir el menú desplegable del origen de datos compartido y, después, haga clic en **Editar definición de origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-128">Click the icon for the expand drop-down menu on shared data source, and then click **Edit Data Source Definition**.</span></span>  
  
     <span data-ttu-id="de7ea-129">Se abre la página Origen de datos.</span><span class="sxs-lookup"><span data-stu-id="de7ea-129">The Data Source page opens.</span></span>  
  
3.  <span data-ttu-id="de7ea-130">Deje las opciones **Tipo de origen de datos** y **Cadena de conexión** tal como están, a menos que desee que el origen de datos compartido se conecte a un tipo diferente de origen de datos, a un servidor diferente o a un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="de7ea-130">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the shared data source to connect to different type of data source, a different server, or data store.</span></span>  
  
4.  <span data-ttu-id="de7ea-131">Para **Credenciales**, seleccione **Credenciales almacenadas**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-131">For **Credentials**, select **Stored credentials**.</span></span>  
  
     <span data-ttu-id="de7ea-132">En algunas circunstancias se puede usar también la opción **No se necesitan credenciales** .</span><span class="sxs-lookup"><span data-stu-id="de7ea-132">The **Credentials are not required** option can also be used under some circumstances.</span></span> <span data-ttu-id="de7ea-133">Esta opción solo funciona si el origen de datos no acepta credenciales o si se pasan credenciales de otra manera.</span><span class="sxs-lookup"><span data-stu-id="de7ea-133">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="de7ea-134">En algunos tipos de orígenes de datos, se debe configurar una cuenta de ejecución desatendida en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="de7ea-134">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="de7ea-135">Para más información, vea el tema del tipo de origen de datos correspondiente en [Agregar datos de orígenes de datos externos &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) y [Configurar la cuenta de ejecución desatendida &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="de7ea-135">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="de7ea-136">Escriba un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="de7ea-136">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="de7ea-137">Si la cuenta es una cuenta de usuario de dominio de Windows, especifíquelo con este formato: \<domain> \\<cuenta \> y, a continuación, seleccione **usar como credenciales de Windows para la conexión al origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="de7ea-137">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>  
  
    -   <span data-ttu-id="de7ea-138">Si el nombre de usuario y la contraseña son credenciales de la base de datos, no seleccione **Utilizar como credenciales de Windows para la conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-138">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="de7ea-139">Si el servidor de base de datos admite la suplantación o la delegación, puede seleccionar **Establecer contexto de ejecución en esta cuenta**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-139">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
6.  <span data-ttu-id="de7ea-140">Para comprobar que el origen de datos se puede conectar usando las credenciales actualizadas, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="de7ea-140">To verify the data source can connect using the updated credentials, **Test connection**.</span></span>  
  
7.  <span data-ttu-id="de7ea-141">Compruebe que la opción Habilitar este origen de datos está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de7ea-141">Verify that Enable this data source is selected.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de7ea-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de7ea-142">See Also</span></span>  
 [<span data-ttu-id="de7ea-143">Cargar documentos en una biblioteca de SharePoint &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="de7ea-143">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
  
