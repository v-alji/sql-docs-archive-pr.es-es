---
title: Ejecutar scripts durante la sincronización (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bc217ad160a0238cc4247600d65eb32f156071f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663366"
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="ffe97-102">Ejecutar scripts durante la sincronización (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ffe97-102">Execute Scripts During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="ffe97-103">La replicación admite la ejecución de script a petición para suscriptores a publicaciones transaccionales y de combinación.</span><span class="sxs-lookup"><span data-stu-id="ffe97-103">Replication supports on demand script execution for Subscribers to transactional and merge publications.</span></span> <span data-ttu-id="ffe97-104">Esta funcionalidad copia el script en el directorio de trabajo de la replicación y, a continuación, usa **sqlcmd** para aplicar el script en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="ffe97-104">This functionality copies the script to the replication working directory and then uses **sqlcmd** to apply the script at the Subscriber.</span></span> <span data-ttu-id="ffe97-105">De forma predeterminada, si hay un error al aplicar el script para una suscripción a una publicación transaccional, el Agente de distribución se detendrá.</span><span class="sxs-lookup"><span data-stu-id="ffe97-105">By default, if there is a failure when applying the script for a subscription to a transactional publication, the Distribution Agent will stop.</span></span> <span data-ttu-id="ffe97-106">Puede especificar que un script [!INCLUDE[tsql](../../includes/tsql-md.md)] se ejecute mediante programación con los procedimientos almacenados de la replicación.</span><span class="sxs-lookup"><span data-stu-id="ffe97-106">You can specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script to execute programmatically using replication stored procedures.</span></span>  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a><span data-ttu-id="ffe97-107">Para especificar que un script se ejecute para todos los suscriptores a una publicación transaccional, de instantáneas o de combinación</span><span class="sxs-lookup"><span data-stu-id="ffe97-107">To specify a script to run for all Subscribers to a snapshot, transactional or merge publication</span></span>  
  
1.  <span data-ttu-id="ffe97-108">Cree y pruebe el script [!INCLUDE[tsql](../../includes/tsql-md.md)] que se ejecutará a petición.</span><span class="sxs-lookup"><span data-stu-id="ffe97-108">Compose and test the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that will be executed on demand.</span></span>  
  
2.  <span data-ttu-id="ffe97-109">Guarde el archivo de script en una ubicación en la que pueda tener acceso el Agente de instantáneas de la publicación.</span><span class="sxs-lookup"><span data-stu-id="ffe97-109">Save the script file to a location where it can be accessed by the Snapshot Agent for the publication.</span></span>  
  
3.  <span data-ttu-id="ffe97-110">En el publicador de la base de datos de publicaciones, ejecute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ffe97-110">At the Publisher on the publication database, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span> <span data-ttu-id="ffe97-111">Especifique \*\* \@ Publication**, el nombre del archivo de script con la ruta UNC completa creada en el paso 2 para \*\* \@ scriptfile**y uno de los siguientes valores para \*\* \@ skiperror\*\*:</span><span class="sxs-lookup"><span data-stu-id="ffe97-111">Specify **\@publication**, the name of the script file with full UNC path created in step 2 for **\@scriptfile**, and one of the following values for **\@skiperror**:</span></span>  
  
    -   <span data-ttu-id="ffe97-112">**0** - el agente dejará de ejecutar el script si se encuentra un error.</span><span class="sxs-lookup"><span data-stu-id="ffe97-112">**0** - the agent will stop executing the script if an error is encountered.</span></span>  
  
    -   <span data-ttu-id="ffe97-113">**1** - el agente registrará los errores y continuará ejecutando el script cuando se encuentren errores.</span><span class="sxs-lookup"><span data-stu-id="ffe97-113">**1** - the agent will log errors and continue executing the script when errors are encountered.</span></span>  
  
4.  <span data-ttu-id="ffe97-114">El script especificado se ejecutará en cada suscriptor cuando el agente se vuelva a ejecutar para sincronizar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="ffe97-114">The specified script will be executed at each Subscriber when the agent next runs to synchronize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe97-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ffe97-115">See Also</span></span>  
 [<span data-ttu-id="ffe97-116">Sincronizar datos</span><span class="sxs-lookup"><span data-stu-id="ffe97-116">Synchronize Data</span></span>](synchronize-data.md)  
  
  
