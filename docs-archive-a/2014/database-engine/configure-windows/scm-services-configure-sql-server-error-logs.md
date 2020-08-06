---
title: Configurar registros de errores de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8acc27150f42049384e2789ef83ae66a737da9bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677885"
---
# <a name="configure-sql-server-error-logs"></a><span data-ttu-id="4143a-102">Configurar registros de errores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4143a-102">Configure SQL Server Error Logs</span></span>
  <span data-ttu-id="4143a-103">En este tema se describe cómo ver o modificar la forma en que se reciclan los registros de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4143a-103">This topic describes how to view or modify the way [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs are recycled.</span></span>  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a><span data-ttu-id="4143a-104">Para abrir el cuadro de diálogo Configurar registros de errores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4143a-104">To open the Configure SQL Server Error Logs dialog box</span></span>  
  
1.  <span data-ttu-id="4143a-105">En el Explorador de objetos, expanda la instancia de SQL Server, expanda **Administración**, haga clic con el botón derecho en **Registros de SQL Server**y después haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="4143a-105">In Object Explorer, expand the instance of SQL Server, expand **Management**, right-click **SQL Server Logs**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="4143a-106">En el cuadro de diálogo **Configurar registros de errores de SQL Server** , elija una de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="4143a-106">In the **Configure SQL Server Error Logs** dialog box, choose from the following options.</span></span>  
  
     <span data-ttu-id="4143a-107">**Limitar el número de archivos de registro de error antes de reciclarlos**</span><span class="sxs-lookup"><span data-stu-id="4143a-107">**Limit the number of the error log files before they are recycled**</span></span>  
     <span data-ttu-id="4143a-108">Actívela para limitar el número de registros de error que se deben crear antes de que se reciclen.</span><span class="sxs-lookup"><span data-stu-id="4143a-108">Check to limit the number of error logs created before they are recycled.</span></span> <span data-ttu-id="4143a-109">Se crea un nuevo registro de errores cada vez que se inicia una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4143a-109">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4143a-110">conserva copias de seguridad de los seis registros anteriores, a menos que se active esta opción y se especifique un número máximo de archivos de registro de errores diferente a continuación.</span><span class="sxs-lookup"><span data-stu-id="4143a-110">retains backups of the previous six logs, unless you check this option, and specify a different maximum number of error log files below.</span></span>  
  
     <span data-ttu-id="4143a-111">**Número máximo de archivos de registro de errores**</span><span class="sxs-lookup"><span data-stu-id="4143a-111">**Maximum number of error log files**</span></span>  
     <span data-ttu-id="4143a-112">Especifica el número máximo de archivos de registro de errores que se pueden crear antes de reciclarse.</span><span class="sxs-lookup"><span data-stu-id="4143a-112">Specify the maximum number of error log files created before they are recycled.</span></span> <span data-ttu-id="4143a-113">El valor predeterminado es 6, que es el número de registros de copia de seguridad anteriores que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserva antes de reciclarlos.</span><span class="sxs-lookup"><span data-stu-id="4143a-113">The default is 6, which is the number of previous backup logs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains before recycling them.</span></span>  
  
  
