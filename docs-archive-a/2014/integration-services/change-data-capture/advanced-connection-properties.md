---
title: Propiedades avanzadas de conexión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4edfab68-7e68-45e8-a3f3-a0049ff7eb9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8dc844d1fdfb1e82f0ffa8de93a6a1060ef190cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674978"
---
# <a name="advanced-connection-properties"></a><span data-ttu-id="668ef-102">Propiedades avanzadas de conexión</span><span class="sxs-lookup"><span data-stu-id="668ef-102">Advanced Connection Properties</span></span>
  <span data-ttu-id="668ef-103">Use el cuadro de diálogo **Propiedades avanzadas de conexión** para agregar más parámetros de conexión a la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="668ef-103">Use the **Advanced Connection Properties** dialog box to add more connection parameters to the connection string.</span></span>  
  
 <span data-ttu-id="668ef-104">Los parámetros de conexión adicionales pueden ser cualquier parámetro de conexión ODBC admitido por la instancia de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que esté usando.</span><span class="sxs-lookup"><span data-stu-id="668ef-104">The additional connection parameters can be any ODBC connection parameter that is supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database instance you are using.</span></span>  
  
 <span data-ttu-id="668ef-105">Los parámetros que se agregan mediante el cuadro de diálogo **Propiedades avanzadas de conexión** se agregan a los parámetros seleccionados en el cuadro de diálogo **Conectar con SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="668ef-105">The parameters added using the **Advanced Connection Properties** dialog box are added to the parameters selected in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="668ef-106">La última instancia de cada parámetro proporcionado invalida cualquier instancia anterior del mismo.</span><span class="sxs-lookup"><span data-stu-id="668ef-106">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="668ef-107">Los parámetros que se agregan mediante el cuadro de diálogo **Parámetros de conexión adicionales** siguen y reemplazan a los parámetros proporcionados en el cuadro de diálogo **Conexión de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="668ef-107">Parameters added using the **Advanced Connection Parameters** dialog box follow and replace the parameters provided in the **SQL Server Connection** dialog box.</span></span> <span data-ttu-id="668ef-108">Por ejemplo, si en el cuadro de diálogo **Conexión de SQL Server** se especifica SERVER1 como el nombre del servidor y la página **Parámetros de conexión adicionales** contiene SERVER=SERVER2, la conexión se realizará con SERVER2.</span><span class="sxs-lookup"><span data-stu-id="668ef-108">For example, if the **SQL Server Connection** dialog box specifies SERVER1 as the Server name, and the **Additional Connection Parameters** page contains ;SERVER=SERVER2, the connection will be made to SERVER2.</span></span>  
  
 <span data-ttu-id="668ef-109">Los parámetros que se agregan mediante el cuadro de diálogo **Propiedades avanzadas de conexión** se pasan como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="668ef-109">Parameters added using the **Advanced Connection Properties** dialog box are passed as plain text.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="668ef-110">No incluya credenciales de inicio de sesión en el cuadro de diálogo **Propiedades avanzadas de conexión** .</span><span class="sxs-lookup"><span data-stu-id="668ef-110">Do not include login credentials in the **Advanced Connection Properties** dialog box.</span></span> <span data-ttu-id="668ef-111">No se cifrarán cuando se pasen a través de la red.</span><span class="sxs-lookup"><span data-stu-id="668ef-111">They will not be encrypted when they are passed across the network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668ef-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="668ef-112">See Also</span></span>  
 <span data-ttu-id="668ef-113">[Obtener acceso a la Consola del diseñador CDC](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="668ef-113">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="668ef-114">Conexión de SQL Server para la creación de instancias</span><span class="sxs-lookup"><span data-stu-id="668ef-114">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
