---
title: Objetos de automatización OLE en Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], OLE Automation
- batches [SQL Server], OLE Automation
- OLE Automation [SQL Server]
- OLE Automation [SQL Server], about OLE Automation
ms.assetid: a887d956-4cd0-400a-aa96-00d7abd7c44b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f36846565bb60fbf875e9babdabbb6d1667f5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678160"
---
# <a name="ole-automation-objects-in-transact-sql"></a><span data-ttu-id="3def6-102">Objetos de automatización OLE en Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3def6-102">OLE Automation Objects in Transact-SQL</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="3def6-103">incluye varios procedimientos almacenados del sistema que permiten hacer referencia a objetos de automatización OLE en los lotes, procedimientos almacenados y desencadenadores de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3def6-103">includes several system stored procedures that allow OLE Automation objects to be referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, stored procedures, and triggers.</span></span> <span data-ttu-id="3def6-104">Estos procedimientos almacenados del sistema se ejecutan como procedimientos almacenados extendidos, y los objetos de automatización OLE que se ejecutan a través de los procedimientos almacenados lo hacen en el espacio de direcciones de una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] de la misma forma que un procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="3def6-104">These system stored procedures run as extended stored procedures, and the OLE Automation objects that are executed through the stored procedures run in the address space of an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the same way that an extended stored procedure runs.</span></span>  
  
 <span data-ttu-id="3def6-105">Los procedimientos almacenados de OLE Automation permiten que los lotes [!INCLUDE[tsql](../../includes/tsql-md.md)] hagan referencia a los objetos SQL-DMO y a los objetos de OLE Automation personalizados, como los objetos que exponen la interfaz **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="3def6-105">The OLE Automation stored procedures enable [!INCLUDE[tsql](../../includes/tsql-md.md)] batches to reference SQL-DMO objects and custom OLE Automation objects, such as objects that expose the **IDispatch** interface.</span></span> <span data-ttu-id="3def6-106">Un servidor OLE personalizado en proceso creado con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] debe tener un controlador de errores (especificado con la instrucción **On Error GoTo**) para las subrutinas **Class_Initialize** y **Class_Terminate**.</span><span class="sxs-lookup"><span data-stu-id="3def6-106">A custom in-process OLE server that is created by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] must have an error handler (specified with the **On Error GoTo** statement) for the **Class_Initialize** and **Class_Terminate** subroutines.</span></span> <span data-ttu-id="3def6-107">Los errores sin controlar de las subrutinas **Class_Initialize** y **Class_Terminate** pueden generar errores impredecibles, como una infracción de acceso en una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3def6-107">Unhandled errors in the **Class_Initialize** and **Class_Terminate** subroutines can cause unpredictable errors, such as an access violation in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="3def6-108">Se recomienda también disponer de identificadores de errores para otras subrutinas.</span><span class="sxs-lookup"><span data-stu-id="3def6-108">Error handlers for other subroutines are also recommended.</span></span>  
  
 <span data-ttu-id="3def6-109">El primer paso a la hora de utilizar un objeto de OLE Automation en [!INCLUDE[tsql](../../includes/tsql-md.md)] es llamar al procedimiento almacenado del sistema **sp_OACreate** para crear una instancia del objeto en el espacio de direcciones del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3def6-109">The first step when using an OLE Automation object in [!INCLUDE[tsql](../../includes/tsql-md.md)] is to call the **sp_OACreate** system stored procedure to create an instance of the object in the address space of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="3def6-110">Una vez creada una instancia del objeto, llame a los siguientes procedimientos almacenados para trabajar con las propiedades, los métodos y la información de error relacionada con el objeto:</span><span class="sxs-lookup"><span data-stu-id="3def6-110">After an instance of the object has been created, call the following stored procedures to work with the properties, methods, and error information related to the object:</span></span>  
  
-   <span data-ttu-id="3def6-111">**sp_OAGetProperty** obtiene el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3def6-111">**sp_OAGetProperty** obtains the value of a property.</span></span>  
  
-   <span data-ttu-id="3def6-112">**sp_OASetProperty** establece el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3def6-112">**sp_OASetProperty** sets the value of a property.</span></span>  
  
-   <span data-ttu-id="3def6-113">**sp_OAMethod** llama a un método.</span><span class="sxs-lookup"><span data-stu-id="3def6-113">**sp_OAMethod** calls a method.</span></span>  
  
-   <span data-ttu-id="3def6-114">**sp_OAGetErrorInfo** obtiene la información de errores más reciente.</span><span class="sxs-lookup"><span data-stu-id="3def6-114">**sp_OAGetErrorInfo** obtains the most recent error information.</span></span>  
  
 <span data-ttu-id="3def6-115">Cuando el objeto deje de ser necesario, llame a **sp_OADestroy** para cancelar la asignación de la instancia del objeto creado con **sp_OACreate**.</span><span class="sxs-lookup"><span data-stu-id="3def6-115">When there is no more need for the object, call **sp_OADestroy** to deallocate the instance of the object created by using **sp_OACreate**.</span></span>  
  
 <span data-ttu-id="3def6-116">Los objetos de automatización OLE devuelven datos a través de valores y métodos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3def6-116">OLE Automation objects return data through property values and methods.</span></span> <span data-ttu-id="3def6-117">**sp_OAGetProperty** y **sp_OAMethod** devuelven estos valores de datos en la forma de un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="3def6-117">**sp_OAGetProperty** and **sp_OAMethod** return these data values in the form of a result set.</span></span>  
  
 <span data-ttu-id="3def6-118">El ámbito de un objeto de OLE Automation se limita a un lote.</span><span class="sxs-lookup"><span data-stu-id="3def6-118">The scope of an OLE Automation object is a batch.</span></span> <span data-ttu-id="3def6-119">Todas las referencias al objeto deben estar contenidas en un único lote, en un procedimiento almacenado o en un desencadenador.</span><span class="sxs-lookup"><span data-stu-id="3def6-119">All references to the object must be contained in a single batch, stored procedure, or trigger.</span></span>  
  
 <span data-ttu-id="3def6-120">Cuando se hace referencia a objetos, los objetos de automatización OLE de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permiten atravesar el objeto referenciado para llegar hasta otros objetos contenidos en él.</span><span class="sxs-lookup"><span data-stu-id="3def6-120">When it references objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation objects support traversing the referenced object to other objects that it contains.</span></span> <span data-ttu-id="3def6-121">Por ejemplo, cuando se usa el objeto **SQLServer** de SQL-DMO, se puede hacer referencia a las bases de datos y tablas contenidas en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="3def6-121">For example, when using the SQL-DMO **SQLServer** object, references can be made to databases and tables contained on that server.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="3def6-122">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="3def6-122">Related Content</span></span>  
 [<span data-ttu-id="3def6-123">Sintaxis de jerarquía de objetos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-123">Object Hierarchy Syntax &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql)  
  
 [<span data-ttu-id="3def6-124">Configuración de Área expuesta</span><span class="sxs-lookup"><span data-stu-id="3def6-124">Surface Area Configuration</span></span>](../security/surface-area-configuration.md)  
  
 [<span data-ttu-id="3def6-125">Ole Automation Procedures (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="3def6-125">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
 [<span data-ttu-id="3def6-126">sp_OACreate &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-126">sp_OACreate &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oacreate-transact-sql)  
  
 [<span data-ttu-id="3def6-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql)  
  
 [<span data-ttu-id="3def6-128">sp_OASetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-128">sp_OASetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql)  
  
 [<span data-ttu-id="3def6-129">sp_OAMethod &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-129">sp_OAMethod &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oamethod-transact-sql)  
  
 [<span data-ttu-id="3def6-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
 [<span data-ttu-id="3def6-131">sp_OADestroy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def6-131">sp_OADestroy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oadestroy-transact-sql)  
  
  
