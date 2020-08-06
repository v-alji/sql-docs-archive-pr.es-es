---
title: Database Mail XPs (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33ee15e862e0992f39373ec30275040c4fcacc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674314"
---
# <a name="database-mail-xps-server-configuration-option"></a><span data-ttu-id="83b18-102">Database Mail XPs (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="83b18-102">Database Mail XPs Server Configuration Option</span></span>
  <span data-ttu-id="83b18-103">Use la opción **DatabaseMail XPs** para habilitar Correo electrónico de base de datos en este servidor.</span><span class="sxs-lookup"><span data-stu-id="83b18-103">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="83b18-104">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="83b18-104">The possible values are:</span></span>  
  
-   <span data-ttu-id="83b18-105">**0** indica que Correo electrónico de base de datos no está disponible (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="83b18-105">**0** indicating Database Mail is not available (default).</span></span>  
  
-   <span data-ttu-id="83b18-106">**1** indica que está disponible Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="83b18-106">**1** indicating Database Mail is available.</span></span>  
  
 <span data-ttu-id="83b18-107">La configuración surte efecto inmediatamente, sin necesidad de detener y reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="83b18-107">The setting takes effect immediately without a server stop and restart.</span></span>  
  
 <span data-ttu-id="83b18-108">Tras habilitar Correo electrónico de base de datos, debe configurar una base de datos host de Correo electrónico de base de datos para usar Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="83b18-108">After enabling Database Mail, you must configure a Database Mail host database to use Database Mail.</span></span>  
  
 <span data-ttu-id="83b18-109">Configurar la base de datos con el **Asistente para configuración del correo electrónico de base de datos** habilita los procedimientos almacenados extendidos de Correo electrónico de base de datos en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="83b18-109">Configuring Database Mail using the **Database Mail Configuration Wizard** enables the Database Mail extended stored procedures in the **msdb** database.</span></span> <span data-ttu-id="83b18-110">Si usa el **Asistente para configuración del correo electrónico de base de datos**, no tiene que usar el siguiente ejemplo de **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="83b18-110">If you use the **Database Mail Configuration Wizard**, you do not have to use the **sp_configure** example below.</span></span>  
  
 <span data-ttu-id="83b18-111">Si establece la opción **Database Mail XPs** en 0, impide que se inicie Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="83b18-111">Setting the **Database Mail XPs** option to 0 prevents Database Mail from starting.</span></span> <span data-ttu-id="83b18-112">Si está en ejecución cuando se establece la opción en 0, continúa ejecutándose y enviando correo hasta que permanece inactivo durante el tiempo configurado en la opción **DatabaseMailExeMinimumLifeTime** .</span><span class="sxs-lookup"><span data-stu-id="83b18-112">If it is running when the option is set to 0, it continues to run and send mail until it is idle for the time configured in the **DatabaseMailExeMinimumLifeTime** option.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="83b18-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="83b18-113">Examples</span></span>  
 <span data-ttu-id="83b18-114">En el ejemplo siguiente se habilitan los procedimientos almacenados extendidos de Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="83b18-114">The following example enables the Database Mail extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="83b18-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83b18-115">See Also</span></span>  
 [<span data-ttu-id="83b18-116">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="83b18-116">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
