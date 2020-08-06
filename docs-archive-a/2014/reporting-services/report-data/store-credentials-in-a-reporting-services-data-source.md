---
title: Almacenamiento de las credenciales en un origen de datos de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 09/23/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- credentials [Reporting Services]
- security [Analysis Services], data sources
- stored credentials [Reporting Services]
- data sources [Reporting Services], stored credentials
ms.assetid: dc700922-97fa-4b30-9547-05bbbec4f09c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fccf8669d1f39d19a26b443ffcead8e86db66a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675220"
---
# <a name="store-credentials-in-a-reporting-services-data-source"></a><span data-ttu-id="7d530-102">Almacenamiento de las credenciales en un origen de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d530-102">Store Credentials in a Reporting Services Data Source</span></span>
  <span data-ttu-id="7d530-103">Es posible configurar credenciales almacenadas que un servidor de informes de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] use para obtener acceso a los datos externos de un informe.</span><span class="sxs-lookup"><span data-stu-id="7d530-103">You can configure stored credentials that a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] report server uses to access external data for a report.</span></span> <span data-ttu-id="7d530-104">Las credenciales almacenadas se utilizan si un informe se ejecuta de forma desatendida, por ejemplo, una suscripción [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que publica un informe como correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7d530-104">Stored credentials are used if the report runs unattended, for example a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription that publishes a report as an e-mail.</span></span> <span data-ttu-id="7d530-105">El servidor de informes recupera y usa las credenciales cuando se programa o desencadena el procesamiento de informes.</span><span class="sxs-lookup"><span data-stu-id="7d530-105">The report server retrieves and uses the credentials when report processing is scheduled or triggered.</span></span> <span data-ttu-id="7d530-106">En este tema se explica cómo configurar credenciales almacenadas para los servidores de informes en modo Nativo y en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7d530-106">This topic walks you through configuring stored credentials for both Native mode and SharePoint mode report servers.</span></span>

||
|-|
|<span data-ttu-id="7d530-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] | Modo de SharePoint de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d530-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="7d530-108">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="7d530-108">**In this topic:**</span></span>

-   [<span data-ttu-id="7d530-109">Configurar credenciales almacenadas para un origen de datos específico de informe (modo Nativo)</span><span class="sxs-lookup"><span data-stu-id="7d530-109">Configure stored credentials for a report-specific data source (Native mode)</span></span>](#bkmk_stored_credentials_data_source_native)

-   [<span data-ttu-id="7d530-110">Configurar credenciales almacenadas para un origen de datos específico de informe (modo de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7d530-110">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_data_source_sharepoint)

-   [<span data-ttu-id="7d530-111">Configurar credenciales almacenadas para un origen de datos compartido (modo Nativo)</span><span class="sxs-lookup"><span data-stu-id="7d530-111">Configure stored credentials for a shared data source (Native mode)</span></span>](#bkmk_stored_credentials_shared_data_source_native)

-   [<span data-ttu-id="7d530-112">Configurar credenciales almacenadas para un origen de datos compartido (modo de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7d530-112">Configure stored credentials for a shared data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_shared_data_source_sharepoint)

##  <a name="security-policy-requirements-for-stored-credentials"></a><a name="bkmk_top"></a> <span data-ttu-id="7d530-113">Requisitos de directiva de seguridad para credenciales almacenadas</span><span class="sxs-lookup"><span data-stu-id="7d530-113">Security policy requirements for stored credentials</span></span>
 <span data-ttu-id="7d530-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") Es necesario que la cuenta que usa para las credenciales almacenadas se configure para una de las siguientes directivas de seguridad en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7d530-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") It is required that the account you use for stored credentials, is configured for one of the following security policies on the report server.</span></span> <span data-ttu-id="7d530-115">Se recomienda seleccionar la directiva con el nivel mínimo de permisos necesario para el entorno.</span><span class="sxs-lookup"><span data-stu-id="7d530-115">It is recommended you select the policy with the minimum level of permissions you require for your environment.</span></span>

1.  <span data-ttu-id="7d530-116">**Permitir el inicio de sesión local**.</span><span class="sxs-lookup"><span data-stu-id="7d530-116">**Allow log on locally**.</span></span> <span data-ttu-id="7d530-117">Para obtener más información, vea [Permitir el inicio de sesión local](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7d530-117">For more information, see [Allow log on locally](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span></span>

2.  <span data-ttu-id="7d530-118">**Iniciar sesión como proceso por lotes**.</span><span class="sxs-lookup"><span data-stu-id="7d530-118">**Log on as a batch job**.</span></span> <span data-ttu-id="7d530-119">Para obtener más información, vea [Iniciar sesión como proceso por lotes](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7d530-119">For more information, see [Log on as a batch job](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span></span>

3.  <span data-ttu-id="7d530-120">Para obtener información general sobre directivas, vea [Modificar la configuración de seguridad en un objeto de directiva de grupo](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7d530-120">For general information on policies, see [Edit security settings on a Group Policy object](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-native-mode"></a><a name="bkmk_stored_credentials_data_source_native"></a><span data-ttu-id="7d530-121">Configurar credenciales almacenadas para un origen de datos específico del informe (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="7d530-121">Configure stored credentials for a report-specific data source (Native mode)</span></span>

1.  <span data-ttu-id="7d530-122">En el modo Nativo del Administrador de informes, vaya a la carpeta que contiene el informe.</span><span class="sxs-lookup"><span data-stu-id="7d530-122">In Native mode Report Manager, browse to the folder that contains the report.</span></span> <span data-ttu-id="7d530-123">Haga clic en el menú contextual del elemento ![en el administrador de informes para elementos de SSRS](../media/ssrs-report-manager-item-context-menu.png "menú contextual en el administrador de informes para elementos de ssrs").</span><span class="sxs-lookup"><span data-stu-id="7d530-123">Click the item context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items").</span></span>

2.  <span data-ttu-id="7d530-124">Haga clic en **Administrar** y luego en **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-124">Click **Manage** and then click **Data Sources**.</span></span>

3.  <span data-ttu-id="7d530-125">Seleccione **Un origen de datos personalizado**.</span><span class="sxs-lookup"><span data-stu-id="7d530-125">Select **A custom data source**.</span></span>

4.  <span data-ttu-id="7d530-126">En la lista **Tipo de origen de datos** , seleccione la extensión de procesamiento de datos que se usa para procesar los datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-126">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="7d530-127">En **cadena de conexión**, especifique la cadena de conexión que utiliza el servidor de informes para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-127">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="7d530-128">En el ejemplo siguiente se muestra una cadena de conexión que se utiliza para conectarse a la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] base de datos:</span><span class="sxs-lookup"><span data-stu-id="7d530-128">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="7d530-129">En **Conectar utilizando**, seleccione **Credenciales almacenadas de forma segura en el servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="7d530-129">For **Connect Using**, select **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="7d530-130">Escriba un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="7d530-130">Type a user name and password.</span></span>

    -   <span data-ttu-id="7d530-131">Si la cuenta es una cuenta de usuario de dominio de Windows, especifíquelo con este formato: \<domain> \\<cuenta \> y, a continuación, seleccione **usar como credenciales de Windows para la conexión al origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="7d530-131">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="7d530-132">Si el nombre de usuario y la contraseña son credenciales de la base de datos, no seleccione **Utilizar como credenciales de Windows para la conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-132">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="7d530-133">Si el servidor de bases de datos admite la suplantación o la delegación, puede seleccionar **Suplantar al usuario autenticado después de realizar una conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-133">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

8.  <span data-ttu-id="7d530-134">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7d530-134">Click **Apply**.</span></span>

     <span data-ttu-id="7d530-135">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [Requisitos de directiva de seguridad para credenciales almacenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="7d530-135">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_data_source_sharepoint"></a><span data-ttu-id="7d530-136">Configurar credenciales almacenadas para un origen de datos específico del informe (modo de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7d530-136">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="7d530-137">Vaya a la biblioteca de documentos que contiene el informe y haga clic en el menú Abrir ![menú contextual de la biblioteca de documentos para elementos de ssrs](../media/ssrs-sharepoint-item-context-menu.png "menú contextual de la biblioteca de documentos para elementos de ssrs").</span><span class="sxs-lookup"><span data-stu-id="7d530-137">Browse to the document library that contains the report and then click the open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

2.  <span data-ttu-id="7d530-138">Haga clic en el segundo menú Abrir ![menú contextual de la biblioteca de documentos para elementos de ssrs](../media/ssrs-sharepoint-item-context-menu.png "menú contextual de la biblioteca de documentos para elementos de ssrs") y, luego, haga clic en **Administrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-138">Click second open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click **Manage Data Sources**.</span></span>

3.  <span data-ttu-id="7d530-139">Haga clic en el nombre del origen de datos **personalizado** que quiere configurar con credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="7d530-139">Click the name of the **Custom** data source you want to configure with stored credentials.</span></span>

4.  <span data-ttu-id="7d530-140">En la lista **Tipo de origen de datos** , seleccione la extensión de procesamiento de datos que se usa para procesar los datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-140">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="7d530-141">En **cadena de conexión**, especifique la cadena de conexión que utiliza el servidor de informes para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-141">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="7d530-142">En el ejemplo siguiente se muestra una cadena de conexión que se utiliza para conectarse a la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] base de datos:</span><span class="sxs-lookup"><span data-stu-id="7d530-142">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="7d530-143">En **Credenciales**, seleccione **Credenciales almacenadas**.</span><span class="sxs-lookup"><span data-stu-id="7d530-143">For **Credentials**, select **Stored Credentials**.</span></span>

7.  <span data-ttu-id="7d530-144">Escriba un **nombre de usuario** y una **contraseña**.</span><span class="sxs-lookup"><span data-stu-id="7d530-144">Type a **user name** and **password**.</span></span>

    -   <span data-ttu-id="7d530-145">Si la cuenta es una cuenta de usuario de dominio de Windows, especifíquelo con este formato: \<domain> \\<cuenta \> y, a continuación, seleccione **usar como credenciales de Windows para la conexión al origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="7d530-145">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="7d530-146">Si el nombre de usuario y la contraseña son credenciales de base de datos, no seleccione **Utilizar como credenciales de Windows**.</span><span class="sxs-lookup"><span data-stu-id="7d530-146">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="7d530-147">Si el servidor de base de datos admite la suplantación o la delegación, puede seleccionar **establecer contexto de ejecución en esta cuenta**.</span><span class="sxs-lookup"><span data-stu-id="7d530-147">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>

8.  <span data-ttu-id="7d530-148">Haga clic en **Ok** (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="7d530-148">Click **ok**.</span></span>

     <span data-ttu-id="7d530-149">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [Requisitos de directiva de seguridad para credenciales almacenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="7d530-149">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-native-mode"></a><a name="bkmk_stored_credentials_shared_data_source_native"></a><span data-ttu-id="7d530-150">Configurar credenciales almacenadas para un origen de datos compartido (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="7d530-150">Configure stored credentials for a shared data source (Native mode)</span></span>

1.  <span data-ttu-id="7d530-151">En el modo Nativo del Administrador de informes, vaya al elemento del origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="7d530-151">In Native mode Report Manager, browse to the shared data source item.</span></span> <span data-ttu-id="7d530-152">![Icono de origen de datos compartido](../media/hlp-16datasource.png "Icono de origen de datos compartido")</span><span class="sxs-lookup"><span data-stu-id="7d530-152">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="7d530-153">Haga clic en el menú contextual del menú contextual del ![Administrador de informes para elementos de SSRS](../media/ssrs-report-manager-item-context-menu.png "menú contextual en el administrador de informes para elementos de ssrs") y, a continuación, haga clic en **administrar**.</span><span class="sxs-lookup"><span data-stu-id="7d530-153">Click the context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items") and then click **Manage**.</span></span>

3.  <span data-ttu-id="7d530-154">En la lista **tipo de origen de datos** , especifique la extensión de procesamiento de datos que se utiliza para procesar datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-154">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

4.  <span data-ttu-id="7d530-155">En **cadena de conexión**, especifique la cadena de conexión que utiliza el servidor de informes para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-155">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="7d530-156">recomienda que no especifique credenciales en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="7d530-156">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="7d530-157">En el ejemplo siguiente se muestra una cadena de conexión que se utiliza para conectarse a la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] base de datos local:</span><span class="sxs-lookup"><span data-stu-id="7d530-157">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

5.  <span data-ttu-id="7d530-158">Escriba un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="7d530-158">Type a user name and password.</span></span>

    -   <span data-ttu-id="7d530-159">Si la cuenta es una cuenta de usuario de dominio de Windows, especifíquelo con este formato: \<domain> \\<cuenta \> y, a continuación, seleccione **usar como credenciales de Windows para la conexión al origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="7d530-159">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="7d530-160">Si el nombre de usuario y la contraseña son credenciales de la base de datos, no seleccione **Utilizar como credenciales de Windows para la conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-160">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="7d530-161">Si el servidor de bases de datos admite la suplantación o la delegación, puede seleccionar **Suplantar al usuario autenticado después de realizar una conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-161">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

6.  <span data-ttu-id="7d530-162">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7d530-162">Click **Apply**.</span></span>

     <span data-ttu-id="7d530-163">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [Requisitos de directiva de seguridad para credenciales almacenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="7d530-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_shared_data_source_sharepoint"></a> <span data-ttu-id="7d530-164">Configurar credenciales almacenadas para un origen de datos compartido (modo de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7d530-164">Configure stored credentials for a shared data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="7d530-165">En la biblioteca de documentos, vaya al elemento de origen de datos compartido.![Icono Origen de datos compartido](../media/hlp-16datasource.png "Icono de origen de datos compartido")</span><span class="sxs-lookup"><span data-stu-id="7d530-165">In the document library, browse to the shared data source item.![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="7d530-166">Haga clic en el menú contextual ![menú contextual de la biblioteca de documentos para elementos de ssrs](../media/ssrs-sharepoint-item-context-menu.png "menú contextual de la biblioteca de documentos para elementos de ssrs") y, luego, haga clic en el segundo menú contextul ![menú contextual de la biblioteca de documentos para elementos de ssrs](../media/ssrs-sharepoint-item-context-menu.png "menú contextual de la biblioteca de documentos para elementos de ssrs").</span><span class="sxs-lookup"><span data-stu-id="7d530-166">Click the context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click the second context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

3.  <span data-ttu-id="7d530-167">Haga clic en **Editar definición de origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="7d530-167">Click **Edit Data Source Definition**.</span></span>

4.  <span data-ttu-id="7d530-168">En la lista **tipo de origen de datos** , especifique la extensión de procesamiento de datos que se utiliza para procesar datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-168">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="7d530-169">En **cadena de conexión**, especifique la cadena de conexión que utiliza el servidor de informes para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7d530-169">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="7d530-170">recomienda que no especifique credenciales en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="7d530-170">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="7d530-171">En el ejemplo siguiente se muestra una cadena de conexión que se utiliza para conectarse a la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] base de datos local:</span><span class="sxs-lookup"><span data-stu-id="7d530-171">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="7d530-172">Escriba un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="7d530-172">Type a user name and password.</span></span>

    -   <span data-ttu-id="7d530-173">Si la cuenta es una cuenta de usuario de dominio de Windows, especifíquelo con este formato: \<domain> \\<cuenta \> y, a continuación, seleccione **usar como credenciales de Windows.**</span><span class="sxs-lookup"><span data-stu-id="7d530-173">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials.**</span></span>

    -   <span data-ttu-id="7d530-174">Si el nombre de usuario y la contraseña son credenciales de base de datos, no seleccione **Utilizar como credenciales de Windows**.</span><span class="sxs-lookup"><span data-stu-id="7d530-174">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="7d530-175">Si el servidor de base de datos admite suplantación o delegación, puede seleccionar **Establecer contexto de ejecución en esta cuenta**.</span><span class="sxs-lookup"><span data-stu-id="7d530-175">If the database server supports impersonation or delegation, you can select **Set Execution context to this account**.</span></span>

7.  <span data-ttu-id="7d530-176">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d530-176">Click **Ok**.</span></span>

     <span data-ttu-id="7d530-177">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [Requisitos de directiva de seguridad para credenciales almacenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="7d530-177">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

## <a name="see-also"></a><span data-ttu-id="7d530-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d530-178">See Also</span></span>
 <span data-ttu-id="7d530-179">[Especificar información de credenciales y conexión para los orígenes de datos de informe](../../integration-services/connection-manager/data-sources.md) [configurar propiedades de orígenes de datos para un informe &#40;administrador de informes&#41;](configure-data-source-properties-for-a-report-report-manager.md) [crear, eliminar o modificar un origen de datos compartido &#40;administrador de informes página de](../create-delete-or-modify-a-shared-data-source-report-manager.md) [propiedades&#41;orígenes de datos](../data-sources-properties-page-report-manager.md) &#40;administrador de informes&#41;página de origen de [datos nueva](../new-data-source-page-report-manager.md) &#40;administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="7d530-179">[Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md) [Configure Data Source Properties for a Report  &#40;Report Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [Data Sources Properties Page &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) [New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md)</span></span>


