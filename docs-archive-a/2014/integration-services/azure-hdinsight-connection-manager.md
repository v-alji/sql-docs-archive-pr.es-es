---
title: Administrador de conexiones de Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPHDICM.F1
- SQL11.DTS.DESIGNER.AFPHDICM.F1
ms.assetid: 850a978d-5dba-45b6-a10e-306aafbc353d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaf2f57fec50a58ad1b7e7578407fb6cf3fa0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744283"
---
# <a name="azure-hdinsight-connection-manager"></a><span data-ttu-id="7e068-102">Administrador de conexiones de Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="7e068-102">Azure HDInsight Connection Manager</span></span>
<span data-ttu-id="7e068-103">El **Administrador de conexiones de Azure HDInsight** permite que un paquete SSIS se conecte a un clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7e068-103">The **Azure HDInsight Connection Manager** enables an SSIS package to connect to an Azure HDInsight cluster.</span></span>

<span data-ttu-id="7e068-104">Para crear y configurar un **Administrador de conexiones de Azure HDInsight**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7e068-104">To create and configure an **Azure HDInsight Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="7e068-105">En el cuadro de diálogo **Agregar administrador de conexiones SSIS**, seleccione **AzureHDInsight** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e068-105">In the **Add SSIS Connection Manager** dialog box, select **AzureHDInsight**, and click **Add**.</span></span>
2. <span data-ttu-id="7e068-106">En el cuadro de diálogo **Azure HDInsight Connection Manager Editor** (Editor del Administrador de conexiones de Azure HDInsight), especifique el **nombre DNS del clúster** (sin el prefijo del protocolo), el **nombre de usuario** y la **contraseña** para conectar el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7e068-106">In the **Azure HDInsight Connection Manager Editor** dialog box, specify the **Cluster DNS name** (without the protocol prefix), **Username**, and **Password** for the HDInsight cluster to connect to.</span></span>
3. <span data-ttu-id="7e068-107">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7e068-107">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="7e068-108">Puede ver las propiedades del Administrador de conexiones que creó en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="7e068-108">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
