---
title: WITH CHECK OPTION no se admite en las vistas que contienen TOP en los modos de compatibilidad 90 o posteriores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TOP clause
- WITH CHECK OPTION clause
ms.assetid: 1b9581d0-bad9-43e0-b8fc-f32d8a8a04ca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee7775c875e33f104341a1da39f5fe6c9326f284
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672379"
---
# <a name="with-check-option-is-not-supported-in-views-that-contain-top-in-90-or-later-compatibility-modes"></a><span data-ttu-id="86fcf-102">WITH CHECK OPTION no se admite en vistas que contengan TOP en el modo de compatibilidad 90 o superior</span><span class="sxs-lookup"><span data-stu-id="86fcf-102">WITH CHECK OPTION is not supported in views that contain TOP in 90 or later compatibility modes</span></span>
  <span data-ttu-id="86fcf-103">El Asesor de actualizaciones detectó una vista que utiliza WITH CHECK OPTION y una cláusula TOP en la instrucción SELECT de la vista o en una vista a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="86fcf-103">Upgrade Advisor detected a view that uses the WITH CHECK OPTION and a TOP clause in the SELECT statement of the view or in a referenced view.</span></span> <span data-ttu-id="86fcf-104">Las vistas definidas de esta manera permiten, de forma errónea, que los datos se puedan modificar a través de la vista, lo que puede producir resultados imprecisos si el modo de compatibilidad de la base de datos se ha establecido en 80 o menos.</span><span class="sxs-lookup"><span data-stu-id="86fcf-104">Views defined this way incorrectly allow data to be modified through the view and may produce inaccurate results when the database compatibility mode is set to 80 and earlier.</span></span> <span data-ttu-id="86fcf-105">Los datos no se pueden insertar o actualizar a través de una vista que utilice WITH CHECK OPTION cuando la vista o una vista a la que se hace referencia utilizan la cláusula TOP y el modo de compatibilidad de la base de datos está establecido en 90 o superior.</span><span class="sxs-lookup"><span data-stu-id="86fcf-105">Data cannot be inserted or updated through a view that uses WITH CHECK OPTION when the view or a referenced view uses the TOP clause and the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="86fcf-106">Componente</span><span class="sxs-lookup"><span data-stu-id="86fcf-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="86fcf-107">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="86fcf-107">Corrective Action</span></span>  
 <span data-ttu-id="86fcf-108">Cuando actualiza, las bases de datos de usuarios conservan su modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="86fcf-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="86fcf-109">Antes de cambiar el modo de compatibilidad de la base de datos a 100 o superior, modifique las vistas que utilizan WITH CHECK OPTION y TOP si se desea permitir la modificación de datos a través de la vista.</span><span class="sxs-lookup"><span data-stu-id="86fcf-109">Before you change the database compatibility mode to 100 or later, modify views that use both WITH CHECK OPTION and TOP if data modification through the view is required.</span></span> <span data-ttu-id="86fcf-110">Para obtener más información, vea [sp_dbcmptlevel &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86fcf-110">For more information, see [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fcf-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86fcf-111">See Also</span></span>  
 <span data-ttu-id="86fcf-112">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="86fcf-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="86fcf-113">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="86fcf-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
