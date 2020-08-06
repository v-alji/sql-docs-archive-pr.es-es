---
title: Programar la actualización de datos y los orígenes de datos que no admiten la autenticación de Windows (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8d875bc-7823-46b7-a939-867cefd4de12
author: minewiskan
ms.author: owend
ms.openlocfilehash: 63e37dec6f334395c0c1812c6f76d750c16c53ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673314"
---
# <a name="schedule-data-refresh-and-data-sources-that-do-not-support-windows-authentication-powerpivot-for-sharepoint"></a><span data-ttu-id="82b4f-102">Actualización de datos programada y orígenes de datos no compatibles con la Autenticación de Windows (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="82b4f-102">Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="82b4f-103">En este tema se describe un flujo de trabajo de nuevos datos de programación de PowerPivot para SharePoint que pueden usar orígenes de datos que **NO** admiten la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="82b4f-103">This topic describes a workflow of PowerPivot for SharePoint schedule data fresh that can use data sources that do **NOT** support Windows Authentication.</span></span> <span data-ttu-id="82b4f-104">Por ejemplo, orígenes de datos Oracle o IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="82b4f-104">For example Oracle or IDM DB2 data sources.</span></span> <span data-ttu-id="82b4f-105">Las ilustraciones y los pasos de este tema hacen referencia a orígenes de datos Oracle, pero se aplica el mismo flujo de trabajo a otros orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="82b4f-105">The illustrations and steps in this topic reference Oracle data sources but the same workflow applies to other data sources.</span></span>  
  
||  
|-|  
|<span data-ttu-id="82b4f-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010 &#124; SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="82b4f-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010 &#124; SharePoint 2013.</span></span>|  
  
 <span data-ttu-id="82b4f-107">**Información general:** Cree dos aplicaciones de destino de almacenamiento seguro</span><span class="sxs-lookup"><span data-stu-id="82b4f-107">**Overview:** Create two Secure Store Target Applications.</span></span> <span data-ttu-id="82b4f-108">Configure la primera aplicación de destino (PowerPivotDataRefresh) para usar las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="82b4f-108">Configure the first target application (PowerPivotDataRefresh) to use Windows credentials.</span></span> <span data-ttu-id="82b4f-109">Configure la segunda aplicación de destino con las credenciales para un origen de datos que no admita la autenticación de Windows, por ejemplo, una base de datos Oracle.</span><span class="sxs-lookup"><span data-stu-id="82b4f-109">Configure the second target application with the credentials for a data source that does not support windows authentication, for example, an Oracle database.</span></span> <span data-ttu-id="82b4f-110">La segunda aplicación de destino también usa la primera aplicación de destino para la cuenta de actualización de datos desatendida.</span><span class="sxs-lookup"><span data-stu-id="82b4f-110">The second target application also uses the first target application for the unattended data refresh account.</span></span>  
  
 <span data-ttu-id="82b4f-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span><span class="sxs-lookup"><span data-stu-id="82b4f-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span></span>  
  
-   <span data-ttu-id="82b4f-112">**(1) PowerPivotDatarefresh:** Un identificador de aplicación de destino de almacén seguro que se establece con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="82b4f-112">**(1) PowerPivotDatarefresh:** A Secure Store Target Application ID that is set with windows authentication.</span></span>  
  
-   <span data-ttu-id="82b4f-113">**(2) OracleAuthentication:** Un identificador de aplicación de destino de almacén seguro que se establece con las credenciales de Oracle.</span><span class="sxs-lookup"><span data-stu-id="82b4f-113">**(2) OracleAuthentication:** A Secure Store Target Application ID that is set with Oracle credentials.</span></span>  
  
-   <span data-ttu-id="82b4f-114">**(3)** la aplicación de servicio PowerPivot está configurada para usar la aplicación de destino "PowerPivotDataRefresh" para la **cuenta de actualización de datos desatendida**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-114">**(3)** The PowerPivot Service application is configure to use the target application "PowerPivotDataRefresh" for the **Unattended Data Refresh Account**.</span></span>  
  
-   <span data-ttu-id="82b4f-115">**(4)** El libro de PowerPivot usa datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="82b4f-115">**(4)** PowerePivot Workbook uses Oracle data.</span></span> <span data-ttu-id="82b4f-116">Los valores de actualización del libro especifican la conexión de origen de datos que usa la aplicación de destino **(2)** para las credenciales.</span><span class="sxs-lookup"><span data-stu-id="82b4f-116">The workbook refresh settings specify the data source connection to use the target application **(2)** for credentials.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82b4f-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82b4f-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="82b4f-118">Existe una aplicación de servicio PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="82b4f-118">A PowerPivot Service Application exists.</span></span>  
  
-   <span data-ttu-id="82b4f-119">Existe una aplicación de servicio de almacenamiento seguro.</span><span class="sxs-lookup"><span data-stu-id="82b4f-119">A Secure Store Service Application exists.</span></span>  
  
-   <span data-ttu-id="82b4f-120">Existe un libro Excel con un modelo de datos de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="82b4f-120">An Excel workbook with a PowerPivot data model exists.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-windows-authentication"></a><span data-ttu-id="82b4f-121">Para crear un identificador de aplicación de destino que use la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="82b4f-121">To Create a Target Application ID that uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="82b4f-122">En administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-122">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="82b4f-123">Haga clic en el nombre de la aplicación de servicio de almacenamiento seguro.</span><span class="sxs-lookup"><span data-stu-id="82b4f-123">Click the name of your secure store service application.</span></span>  
  
3.  <span data-ttu-id="82b4f-124">En la página **Administrar** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-124">On the **Manage** page, click **New**.</span></span> <span data-ttu-id="82b4f-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span><span class="sxs-lookup"><span data-stu-id="82b4f-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span></span>  
  
4.  <span data-ttu-id="82b4f-126">En la página **Crear nueva aplicación de destino de almacenamiento seguro** , configure los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="82b4f-126">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="82b4f-127">**Identificador de la aplicación de destino:** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="82b4f-127">**Target Application ID:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="82b4f-128">**Nombre para mostrar:** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="82b4f-128">**Display Name:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="82b4f-129">**Correo electrónico de contacto:** ?</span><span class="sxs-lookup"><span data-stu-id="82b4f-129">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="82b4f-130">**Tipo de aplicación de destino:** Grupo.</span><span class="sxs-lookup"><span data-stu-id="82b4f-130">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="82b4f-131">**Dirección URL de la página de la aplicación de destino:** Ninguna.</span><span class="sxs-lookup"><span data-stu-id="82b4f-131">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="82b4f-132">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="82b4f-133">En la página Credenciales, deje los dos valores predeterminados de nombre de campo y tipos de campo para **Nombre de usuario Windows** y **Contraseña de Windows**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-133">On the Credentials page, leave the two default field names and field types for **Windows User Name** and **Windows Password**.</span></span>  
  
7.  <span data-ttu-id="82b4f-134">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-134">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="82b4f-135">En la página **Configuración de pertenencia** , agregue al menos un **Administrador de aplicación de destino** y, a continuación, agregue los miembros que necesiten acceso a la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="82b4f-135">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="82b4f-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-136">Click **OK**.</span></span>  
  
10. <span data-ttu-id="82b4f-137">El nuevo identificador de aplicación de destino se agrega a la lista.</span><span class="sxs-lookup"><span data-stu-id="82b4f-137">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="82b4f-138">Seleccione el identificador de la aplicación de destino y haga clic en **establecer credenciales**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="82b4f-138">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="82b4f-139">Escriba el nombre de usuario Windows y la contraseña de Windows y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-139">Type the Windows User Name and Windows Password and then click **OK**.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-oracle-credentials"></a><span data-ttu-id="82b4f-140">Para crear un identificador de aplicación de destino que use las credenciales de Oracle</span><span class="sxs-lookup"><span data-stu-id="82b4f-140">To Create a Target Application ID that uses Oracle credentials</span></span>  
  
1.  <span data-ttu-id="82b4f-141">En administración central de SharePoint, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-141">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="82b4f-142">Haga clic en el nombre de la aplicación de servicio de almacenamiento seguro.</span><span class="sxs-lookup"><span data-stu-id="82b4f-142">Click the name of your Secure Store Service application.</span></span>  
  
3.  <span data-ttu-id="82b4f-143">En la página **administrar** , haga clic en **nuevo**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span><span class="sxs-lookup"><span data-stu-id="82b4f-143">On the **Manage** page, click **New**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span></span>  
  
4.  <span data-ttu-id="82b4f-144">En la página **Crear nueva aplicación de destino de almacenamiento seguro** , configure los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="82b4f-144">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="82b4f-145">**Identificador de aplicación de destino:** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="82b4f-145">**Target Application ID:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="82b4f-146">**Nombre para mostrar:** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="82b4f-146">**Display Name:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="82b4f-147">**Correo electrónico de contacto:** ?</span><span class="sxs-lookup"><span data-stu-id="82b4f-147">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="82b4f-148">**Tipo de aplicación de destino:** Grupo.</span><span class="sxs-lookup"><span data-stu-id="82b4f-148">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="82b4f-149">**Dirección URL de la página de la aplicación de destino:** Ninguna.</span><span class="sxs-lookup"><span data-stu-id="82b4f-149">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="82b4f-150">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="82b4f-151">En la página **credenciales** , cambie el primer nombre de campo a `Oracle User ID` y cambie el **tipo de campo** a `User Name` .</span><span class="sxs-lookup"><span data-stu-id="82b4f-151">On the **Credentials** page, change the first field name to `Oracle User ID` and change the **Field Type** to `User Name`.</span></span>  
  
     <span data-ttu-id="82b4f-152">Cambie el segundo nombre de campo a `Oracle Password` y el **tipo de campo** a `Password` .</span><span class="sxs-lookup"><span data-stu-id="82b4f-152">Change the second field name to `Oracle Password` and the **Field Type** to `Password`.</span></span>  
  
7.  <span data-ttu-id="82b4f-153">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-153">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="82b4f-154">En la página **Configuración de pertenencia** , agregue al menos un **Administrador de aplicación de destino** y, a continuación, agregue los miembros que necesiten acceso a la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="82b4f-154">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="82b4f-155">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-155">Click **OK**.</span></span>  
  
10. <span data-ttu-id="82b4f-156">El nuevo identificador de aplicación de destino se agrega a la lista.</span><span class="sxs-lookup"><span data-stu-id="82b4f-156">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="82b4f-157">Seleccione el identificador de la aplicación de destino y haga clic en **establecer credenciales**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="82b4f-157">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="82b4f-158">Escriba el identificador de usuario Oracle y la contraseña de Oracle y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-158">Type the Oracle User ID and Oracle Password and then click **OK**.</span></span>  
  
 <span data-ttu-id="82b4f-159">Para obtener más información, vea la sección "para crear una aplicación de destino para la autenticación de SQL Server" en [usar almacenamiento seguro con autenticación de SQL Server (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) ( https://technet.microsoft.com/library/gg298949.aspx) .</span><span class="sxs-lookup"><span data-stu-id="82b4f-159">For more information, see section "To Create a target application for SQL Server Authentication" in [Use Secure Store with SQL Server Authentication (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) (https://technet.microsoft.com/library/gg298949.aspx).</span></span>  
  
## <a name="to-configure-the-powerpivot-service-application"></a><span data-ttu-id="82b4f-160">Para configurar la aplicación de servicio PowerPivot</span><span class="sxs-lookup"><span data-stu-id="82b4f-160">To Configure the PowerPivot Service Application</span></span>  
  
1.  <span data-ttu-id="82b4f-161">En Administración central de SharePoint, haga clic en Administrar aplicaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="82b4f-161">In SharePoint central administration, click Manage Service Applications.</span></span>  
  
2.  <span data-ttu-id="82b4f-162">Haga clic en el nombre de la aplicación de servicio PowerPivot, por ejemplo "aplicación de servicio PowerPivot predeterminada".</span><span class="sxs-lookup"><span data-stu-id="82b4f-162">Click the name of your PowerPivot Service Application, for example "Default PowerPivot Service Application".</span></span>  
  
3.  <span data-ttu-id="82b4f-163">Haga clic en **Configurar las opciones de aplicación de servicio** en la sección Acciones.</span><span class="sxs-lookup"><span data-stu-id="82b4f-163">Click **Configure service application settings** in the Actions section.</span></span>  
  
4.  <span data-ttu-id="82b4f-164">En la sección **actualización de datos** , establezca la cuenta de actualización de **datos desatendida de PowerPivot**en `PowerPivotDataRefresh` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-164">In the **Data Refresh** section, set the **PowerPivot Unattended Data Refresh Account**to`PowerPivotDataRefresh` and then click **OK**.</span></span>  
  
     <span data-ttu-id="82b4f-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span><span class="sxs-lookup"><span data-stu-id="82b4f-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span></span>  
  
## <a name="to-configure-the-workbook"></a><span data-ttu-id="82b4f-166">Para configurar el libro</span><span class="sxs-lookup"><span data-stu-id="82b4f-166">To configure the workbook</span></span>  
  
1.  <span data-ttu-id="82b4f-167">Busque el libro en la galería de PowerPivot y haga clic en **administrar**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh")de actualización de datos.</span><span class="sxs-lookup"><span data-stu-id="82b4f-167">Browse to your workbook in the PowerPivot Gallery and click **Manage Data Refresh**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span></span>  
  
2.  <span data-ttu-id="82b4f-168">Si aparece la página **Historial de actualización de datos** , haga clic en **Configurar programación**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-168">If you see the **Data Refresh History** page, click **Configure Schedule**.</span></span>  
  
3.  <span data-ttu-id="82b4f-169">Haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-169">Click **Enable**.</span></span>  
  
4.  <span data-ttu-id="82b4f-170">Haga clic en **También actualizar lo más rápido posible**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-170">Click **Also Refresh as soon as possible**.</span></span>  
  
5.  <span data-ttu-id="82b4f-171">En la sección **Credenciales** , haga clic en **Usar la cuenta de actualización de datos configurada por el administrador**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-171">In the **Credentials** section, click **Use the Data refresh account configured by the administrator**.</span></span>  
  
6.  <span data-ttu-id="82b4f-172">Desactive **Todos los orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-172">Clear **All data sources**.</span></span>  
  
7.  <span data-ttu-id="82b4f-173">Seleccione **Actualizar** para el origen de datos que usa los datos Oracle.</span><span class="sxs-lookup"><span data-stu-id="82b4f-173">Select **Refresh** for the data source that uses the Oracle data.</span></span> <span data-ttu-id="82b4f-174">El nombre del origen de datos puede cambiarse en Microsoft Excel en el menú **Datos**, **Conexiones**, **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="82b4f-174">The name of the data source name can be changed in Microsoft Excel in the **Data**, **Connections**, **Properties** menu.</span></span>  
  
8.  <span data-ttu-id="82b4f-175">En el origen de datos, seleccione **Usar programación predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-175">Under your data source, Select **Use Default Schedule**.</span></span>  
  
9. <span data-ttu-id="82b4f-176">Seleccione **Conectar con las credenciales guardadas en el servicio de almacenamiento seguro (SSS) para iniciar sesión en el origen de datos. Especifique el identificador usado para buscar las credenciales en el cuadro de identificador de SSS**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-176">Select **Connect using the credentials saved in Secure Store Service (SSS) to log on to the data source. Enter the ID used to look up the credentials in the SSS ID box**.</span></span>  
  
10. <span data-ttu-id="82b4f-177">En el cuadro **ID.:** , escriba `OracleAuthentication` .</span><span class="sxs-lookup"><span data-stu-id="82b4f-177">In the **ID:** box, type `OracleAuthentication`.</span></span>  
  
11. <span data-ttu-id="82b4f-178">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-178">Click **OK**.</span></span>  
  
     <span data-ttu-id="82b4f-179">Si se muestra un mensaje de error similar al siguiente: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span><span class="sxs-lookup"><span data-stu-id="82b4f-179">If you see an error message similar to: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span></span>  
  
     <span data-ttu-id="82b4f-180">Las dos soluciones comunes son:</span><span class="sxs-lookup"><span data-stu-id="82b4f-180">The two common solutions are:</span></span>  
  
    -   <span data-ttu-id="82b4f-181">Compruebe que el identificador de la aplicación de destino es correcto.</span><span class="sxs-lookup"><span data-stu-id="82b4f-181">Verify that the Target Application ID is correct.</span></span>  
  
    -   <span data-ttu-id="82b4f-182">Compruebe que ha establecido las credenciales para la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="82b4f-182">Verify that you set credentials for the Target Application.</span></span>  
  
## <a name="to-verify-data-refresh-with-the-new-authentication"></a><span data-ttu-id="82b4f-183">Para comprobar la actualización de datos con la nueva autenticación</span><span class="sxs-lookup"><span data-stu-id="82b4f-183">To Verify Data Refresh with the new authentication</span></span>  
 <span data-ttu-id="82b4f-184">Cuando haga clic en **Aceptar**, se mostrará la página **Historial de actualización** .</span><span class="sxs-lookup"><span data-stu-id="82b4f-184">When you click **ok**, you see the **Refresh History** page.</span></span> <span data-ttu-id="82b4f-185">En unos pocos minutos, debe aparecer un nuevo elemento en el historial de actualización porque en los pasos anteriores seleccionó **También actualizar lo más rápido posible**.</span><span class="sxs-lookup"><span data-stu-id="82b4f-185">Within a few minutes, you should see a new item in the refresh history because in the previous steps you selected **Also Refresh as soon as possible**.</span></span> <span data-ttu-id="82b4f-186">El valor predeterminado para el trabajo del temporizador **Trabajo de temporizador de actualización de datos PowerPivot** es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="82b4f-186">The default value for the timer job **PowerPivot Data Refresh Timer Job** is 1 minute.</span></span> <span data-ttu-id="82b4f-187">Si no aparece un nuevo elemento en el historial de actualización, espere unos minutos y actualice el explorador.</span><span class="sxs-lookup"><span data-stu-id="82b4f-187">If you do not see a new item in the refresh history, wait a few minutes and refresh your browser.</span></span> <span data-ttu-id="82b4f-188">Si todavía no aparece el nuevo elemento, compruebe el valor actual de trabajo del temporizador.</span><span class="sxs-lookup"><span data-stu-id="82b4f-188">If you still do not see the new item, verify the current value of the timer job.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="82b4f-189">Más información</span><span class="sxs-lookup"><span data-stu-id="82b4f-189">More Information</span></span>  
  
-   <span data-ttu-id="82b4f-190">[Configurar el Servicio de almacenamiento seguro de SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span><span class="sxs-lookup"><span data-stu-id="82b4f-190">[Configure the Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span></span>  
  
-   <span data-ttu-id="82b4f-191">Vea la sección "actualización de datos programada" de [actualización de datos PowerPivot con SharePoint 2013 y SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span><span class="sxs-lookup"><span data-stu-id="82b4f-191">See the "Scheduled Data Refresh" section of [PowerPivot Data Refresh with SharePoint 2013 and SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span></span>  
  
  
