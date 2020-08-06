---
title: Administrador de conexiones de Azure Storage | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpstorageconn.f1
- sql11.dts.designer.afpstorageconn.f1
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47580d8d1d961df9fbcbed0bd7164f1c54792b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673223"
---
# <a name="azure-storage-connection-manager"></a><span data-ttu-id="a0afd-102">Administrador de conexiones de Almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="a0afd-102">Azure Storage Connection Manager</span></span>
  <span data-ttu-id="a0afd-103">El Administrador de conexiones de Azure Storage habilita un paquete SSIS para conectarse a una cuenta de Azure Storage utilizando los valores especificados para las propiedades nombre de cuenta y clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a0afd-103">The Azure Storage connection manager enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.</span></span>  
  
1.  <span data-ttu-id="a0afd-104">En el cuadro de diálogo **Agregar administrador de conexiones SSIS** , seleccione **AzureStorage**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a0afd-104">In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="a0afd-105">En el cuadro de diálogo Azure Storage Connection Manager Editor (Editor del administrador de conexiones de Almacenamiento de Azure), elija **Use Azure account** (Usar cuenta de Azure) para conectarse a un servicio de Almacenamiento de Azure a través de Internet o elija **Use local developer account** (Usar cuenta de desarrollador local) para conectarse al servicio local hospedado en el Emulador de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="a0afd-105">In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.</span></span>  
  
3.  <span data-ttu-id="a0afd-106">Si ha seleccionado la opción **Use Azure account** (Usar cuenta de Azure), realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0afd-106">If you selected **Use Azure account** option, do the following:</span></span>  
  
    1.  <span data-ttu-id="a0afd-107">Especifique los valores para los campos **Nombre de cuenta de almacenamiento** y **Clave de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="a0afd-107">Specify values for the **Storage account name** and **Account key** field.</span></span> <span data-ttu-id="a0afd-108">Estos valores se almacenarán como información confidencial en el paquete SSIS.</span><span class="sxs-lookup"><span data-stu-id="a0afd-108">These values will be stored as sensitive data in SSIS package.</span></span>  
  
    2.  <span data-ttu-id="a0afd-109">Seleccione **Use HTTPS** (Usar HTTPS) si desea utilizar HTTPS en lugar de HTTP para conectarse con el servicio de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="a0afd-109">Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.</span></span>  
  
4.  <span data-ttu-id="a0afd-110">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a0afd-110">Click **OK** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="a0afd-111">Puede ver las propiedades del Administrador de conexiones que creó en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="a0afd-111">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
