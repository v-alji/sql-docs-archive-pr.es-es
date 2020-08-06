---
title: Registro de paquetes con equilibrio de carga en servidores remotos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], remote packages
ms.assetid: fd571567-b625-4f9a-8b7e-42c5c588b11b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b45fa6607d6edc1559d8ebcbbbc7598e11eac408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673101"
---
# <a name="logging-for-load-balanced-packages-on-remote-servers"></a><span data-ttu-id="0e2b0-102">Registro para la carga de paquetes equilibrados en servidores remotos</span><span class="sxs-lookup"><span data-stu-id="0e2b0-102">Logging for Load Balanced Packages on Remote Servers</span></span>
  <span data-ttu-id="0e2b0-103">Para un administrador es más fácil administrar los registros de todos los paquetes secundarios que están en ejecución en varios servidores cuando todos los paquetes secundarios utilizan el mismo proveedor de registro y todos escriben en el mismo destino.</span><span class="sxs-lookup"><span data-stu-id="0e2b0-103">It is easier for an administrator to manage the logs for all the child packages that are running on various servers when all the child packages use the same log provider and they all write to the same destination.</span></span> <span data-ttu-id="0e2b0-104">Una manera de crear un archivo común de registro para todos los paquetes secundarios es configurar los paquetes secundarios para que registren sus eventos en un proveedor de registro de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e2b0-104">One way that you can create a common log file for all child packages is to configure the child packages to log their events to a SQL Server log provider.</span></span> <span data-ttu-id="0e2b0-105">Puede configurar todos los paquetes para que utilicen la misma base de datos, el mismo servidor y la misma instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="0e2b0-105">You can configure all the packages to use the same database, the same server, and the same instance of the server.</span></span>  
  
 <span data-ttu-id="0e2b0-106">Para ver los archivos de registro, el administrador solo tiene que registrarse en un único servidor para ver los archivos de registro de todos los paquetes secundarios.</span><span class="sxs-lookup"><span data-stu-id="0e2b0-106">To view the log files, the administrator only has to log on to a single server to view the log files for all child packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0e2b0-107">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0e2b0-107">Related Tasks</span></span>  
 <span data-ttu-id="0e2b0-108">Para obtener información sobre cómo habilitar el registro en un paquete, vea [Habilitar el registro de paquetes en SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0e2b0-108">For information about how to enable logging in a package, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2b0-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e2b0-109">See Also</span></span>  
 [<span data-ttu-id="0e2b0-110">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e2b0-110">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
