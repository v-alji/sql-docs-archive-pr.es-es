---
title: Administrador de conexiones de suscripciones de Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpsubscrconn.f1
- sql11.dts.designer.afpsubscrconn.f1
ms.assetid: e1225327-c308-4c50-8f44-c411f52ef378
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bff1286525983b32c2191f1f8864a0f2bef0e6b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673218"
---
# <a name="azure-subscription-connection-manager"></a><span data-ttu-id="f9dad-102">Azure Subscription Connection Manager (Administrador de conexiones de suscripciones de Azure)</span><span class="sxs-lookup"><span data-stu-id="f9dad-102">Azure Subscription Connection Manager</span></span>
  <span data-ttu-id="f9dad-103">El administrador de conexiones de HDInsight de Azure permite que un paquete de SSIS se conecte con una suscripción de Azure a través de los valores que especifica para las propiedades: id. de suscripción de Azure y certificado de administración.</span><span class="sxs-lookup"><span data-stu-id="f9dad-103">The Azure HDInsight connection manager enables an SSIS package to connect to an Azure subscription by using the values you specify for the properties: Azure Subscription ID and Management Certificate.</span></span>

1.  <span data-ttu-id="f9dad-104">En el cuadro de diálogo **Agregar administrador de conexiones SSIS** que se muestra arriba, seleccione **Suscripción de Azure**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9dad-104">In the **Add SSIS Connection Manager** dialog box shown above, you select **Azure Subscription**, and click **Add**.</span></span>  <span data-ttu-id="f9dad-105">Debería aparecer el cuadro de diálogo **Azure Subscription Connection Manager Editor** (Editor de administrador de conexiones de suscripciones de Azure).</span><span class="sxs-lookup"><span data-stu-id="f9dad-105">You should see the following **Azure Subscription Connection Manager Editor** dialog box.</span></span>

     <span data-ttu-id="f9dad-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span><span class="sxs-lookup"><span data-stu-id="f9dad-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span></span>

2.  <span data-ttu-id="f9dad-107">Escriba el id. de suscripción de Azure, que identifica una suscripción de Azure de manera única, para el **id. de suscripción de Azure**.</span><span class="sxs-lookup"><span data-stu-id="f9dad-107">Enter your Azure subscription ID, which uniquely identifies an Azure subscription, for the **Azure subscription ID**.</span></span>  <span data-ttu-id="f9dad-108">Se puede encontrar el valor en el [Portal de administración de Azure](https://manage.windowsazure.com) en la página **Configuración** :</span><span class="sxs-lookup"><span data-stu-id="f9dad-108">The value can be found on the [Azure Management Portal](https://manage.windowsazure.com) under **Settings** page:</span></span>

     <span data-ttu-id="f9dad-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span><span class="sxs-lookup"><span data-stu-id="f9dad-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span></span>

3.  <span data-ttu-id="f9dad-110">Elija **Management certificate store location** (Ubicación de almacén de certificados de administración) y **Management certificate store name** (Nombre de almacén de certificados de administración) en las listas desplegables.</span><span class="sxs-lookup"><span data-stu-id="f9dad-110">Choose **Management certificate store location** and **Management certificate store name** from the drop-down lists.</span></span>

4.  <span data-ttu-id="f9dad-111">Escriba **Management certificate thumbprint** (Huella digital de certificado de administración) o haga clic en **Examinar…** para elegir un certificado en el almacén seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f9dad-111">Enter **Management certificate thumbprint** or click the **Browse...** to choose a certificate from the selected store.</span></span> <span data-ttu-id="f9dad-112">El certificado se debe cargar como un certificado de administración para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="f9dad-112">The certificate must be uploaded as a management certificate for the subscription.</span></span> <span data-ttu-id="f9dad-113">Para hacerlo, haga clic en **Cargar** en la página siguiente de Azure Portal (consulte esta [publicación de MSDN](https://msdn.microsoft.com/library/azure/gg551722.aspx) para obtener más detalles).</span><span class="sxs-lookup"><span data-stu-id="f9dad-113">To do so, click **Upload** on the following page of the Azure Portal (see this [MSDN post](https://msdn.microsoft.com/library/azure/gg551722.aspx) for more detail).</span></span>

     <span data-ttu-id="f9dad-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span><span class="sxs-lookup"><span data-stu-id="f9dad-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span></span>

5.  <span data-ttu-id="f9dad-115">Haga clic en **probar conexión** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="f9dad-115">Click **Test Connection** to test the connection.</span></span>

6.  <span data-ttu-id="f9dad-116">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f9dad-116">Click **OK** to close the dialog box.</span></span>


