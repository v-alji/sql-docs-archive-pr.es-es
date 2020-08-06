---
title: WITH ROWS no se admite en las instrucciones CREATE STATISTICs en el modo de compatibilidad de 90 o posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH ROWS in CREATE STATISTICS statement
ms.assetid: 197b2ecf-a1a3-4a3a-a523-a0ee919c1dde
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d28a05e7cd025e213e2cebdce9d582a9df446fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672378"
---
# <a name="with-rows-is-not-supported-in-create-statistics-statements-in-the-compatibility-mode-of-90-or-later"></a><span data-ttu-id="0eb2c-102">No se admite WITH ROW en instrucciones CREATE STATISTICS en el modo de compatibilidad de 90 o superior</span><span class="sxs-lookup"><span data-stu-id="0eb2c-102">WITH ROWS is not supported in CREATE STATISTICS statements in the compatibility mode of 90 or later</span></span>
  <span data-ttu-id="0eb2c-103">No se admite el uso de WITH ROWS en instrucciones CREATE STATISTICS si se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el modo de compatibilidad establecido en 90 o más.</span><span class="sxs-lookup"><span data-stu-id="0eb2c-103">Specifying WITH ROWS in CREATE STATISTICS statements is not supported when you run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set to the compatibility mode of 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0eb2c-104">Componente</span><span class="sxs-lookup"><span data-stu-id="0eb2c-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="0eb2c-105">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="0eb2c-105">Corrective Action</span></span>  
 <span data-ttu-id="0eb2c-106">Modifique las instrucciones CREATE STATISTICs que incluyan WITH ROWS especificando con filas de *número* de muestra o especificando otras opciones que cumplan con la sintaxis documentada.</span><span class="sxs-lookup"><span data-stu-id="0eb2c-106">Modify CREATE STATISTICS statements that include WITH ROWS by specifying WITH SAMPLE *number* ROWS, or by specifying other options that comply with the documented syntax.</span></span> <span data-ttu-id="0eb2c-107">Para obtener más información, vea el tema "CREATE STATISTICs (Transact-SQL) en Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eb2c-107">For more information, see the topic "CREATE STATISTICS (Transact-SQL) in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb2c-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0eb2c-108">See Also</span></span>  
 <span data-ttu-id="0eb2c-109">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="0eb2c-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="0eb2c-110">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="0eb2c-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
