---
title: Objeto SqlContext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- Windows identity [CLR integration]
- SqlContext object
- context [CLR integration]
ms.assetid: 67437853-8a55-44d9-9337-90689ebba730
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f036e274925f7b28b79f619f8e24b3e8804140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747035"
---
# <a name="sqlcontext-object"></a><span data-ttu-id="e7cdb-102">Objeto SqlContext</span><span class="sxs-lookup"><span data-stu-id="e7cdb-102">SqlContext Object</span></span>
  <span data-ttu-id="e7cdb-103">Se invoca el código administrado en el servidor al llamar a un procedimiento o función, al llamar a un método en un tipo definido por el usuario de Common Language Runtime (CLR) o cuando su acción activa un desencadenador definido en cualquiera de los lenguajes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-103">You invoke managed code in the server when you call a procedure or function, when you call a method on a common language runtime (CLR) user-defined type, or when your action fires a trigger defined in any of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework languages.</span></span> <span data-ttu-id="e7cdb-104">Dado que la ejecución de este código se solicita como parte de una conexión de usuario, se requiere el acceso al contexto del autor de la llamada desde el código que se ejecuta en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-104">Because execution of this code is requested as part of a user connection, access to the context of the caller from the code running in the server is required.</span></span> <span data-ttu-id="e7cdb-105">Además, ciertas operaciones de acceso a datos solo pueden ser válidas si se ejecutan bajo el contexto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-105">In addition, certain data access operations may only be valid if run under the context of the caller.</span></span> <span data-ttu-id="e7cdb-106">Por ejemplo, el acceso a pseudo tablas insertadas y eliminadas utilizadas en operaciones del desencadenador solo es válido bajo el contexto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-106">For example, access to inserted and deleted pseudo-tables used in trigger operations is only valid under the context of the caller.</span></span>  
  
 <span data-ttu-id="e7cdb-107">El contexto del autor de la llamada se resume en un objeto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-107">The context of the caller is abstracted in a `SqlContext` object.</span></span> <span data-ttu-id="e7cdb-108">Para obtener más información sobre los métodos y propiedades de `SqlTriggerContext`, vea la documentación de referencia de clase `Microsoft.SqlServer.Server.SqlTriggerContext` en [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-108">For more information about the `SqlTriggerContext` methods and properties, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="e7cdb-109">`SqlContext` proporciona acceso a los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7cdb-109">`SqlContext` provides access to the following components:</span></span>  
  
-   <span data-ttu-id="e7cdb-110">`SqlPipe`: el objeto `SqlPipe` representa la "canalización" a través de la que los resultados fluyen al cliente.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-110">`SqlPipe`: The `SqlPipe` object represents the "pipe" through which results flow to the client.</span></span> <span data-ttu-id="e7cdb-111">Para obtener más información sobre el `SqlPipe` objeto, vea [SqlPipe (objeto](sqlpipe-object.md)).</span><span class="sxs-lookup"><span data-stu-id="e7cdb-111">For more information about the `SqlPipe` object, see [SqlPipe Object](sqlpipe-object.md).</span></span>  
  
-   <span data-ttu-id="e7cdb-112">`SqlTriggerContext`: el objeto `SqlTriggerContext` solo se puede recuperar desde un desencadenador CLR.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-112">`SqlTriggerContext`: The `SqlTriggerContext` object can only be retrieved from within a CLR trigger.</span></span> <span data-ttu-id="e7cdb-113">Proporciona información sobre la operación que hizo que se activara el desencadenador y un mapa de las columnas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-113">It provides information about the operation that caused the trigger to fire and a map of the columns that were updated.</span></span> <span data-ttu-id="e7cdb-114">Para obtener más información sobre el `SqlTriggerContext` objeto, vea [objeto SqlTriggerContext](sqltriggercontext-object.md).</span><span class="sxs-lookup"><span data-stu-id="e7cdb-114">For more information about the `SqlTriggerContext` object, see [SqlTriggerContext Object](sqltriggercontext-object.md).</span></span>  
  
-   <span data-ttu-id="e7cdb-115">`IsAvailable`: la propiedad `IsAvailable` se utiliza para determinar la disponibilidad de contexto.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-115">`IsAvailable`: The `IsAvailable` property is used to determine context availability.</span></span>  
  
-   <span data-ttu-id="e7cdb-116">`WindowsIdentity`: la propiedad `WindowsIdentity` se utiliza para recuperar la identidad de Windows del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-116">`WindowsIdentity`: The `WindowsIdentity` property is used to retrieve the Windows identity of the caller.</span></span>  
  
## <a name="determining-context-availability"></a><span data-ttu-id="e7cdb-117">Determinar la disponibilidad del contexto</span><span class="sxs-lookup"><span data-stu-id="e7cdb-117">Determining Context Availability</span></span>  
 <span data-ttu-id="e7cdb-118">Consulte la clase `SqlContext` para ver si el código actualmente en ejecución se ejecuta en proceso.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-118">Query the `SqlContext` class to see if the currently executing code is running in-process.</span></span> <span data-ttu-id="e7cdb-119">Para ello, compruebe la propiedad `IsAvailable` del objeto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-119">To do this, check the `IsAvailable` property of the `SqlContext` object.</span></span> <span data-ttu-id="e7cdb-120">La propiedad `IsAvailable` es de solo lectura y devuelve `True` si el código de llamada se está ejecutando dentro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y si se puede tener acceso a otros miembros de `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-120">The `IsAvailable` property is read-only, and returns `True` if the calling code is running inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and if other `SqlContext` members can be accessed.</span></span> <span data-ttu-id="e7cdb-121">Si la propiedad `IsAvailable` devuelve `False`, todos los demás miembros de `SqlContext` producen una excepción `InvalidOperationException`, si se utilizan.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-121">If the `IsAvailable` property returns `False`, all the other `SqlContext` members throw an `InvalidOperationException`, if used.</span></span> <span data-ttu-id="e7cdb-122">Si `IsAvailable` devuelve `False`, cualquier intento de abrir un objeto de conexión con "context connection=true" en la cadena de conexión genera un error.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-122">If `IsAvailable` returns `False`, any attempt to open a connection object that has "context connection=true" in the connection string fails.</span></span>  
  
## <a name="retrieving-windows-identity"></a><span data-ttu-id="e7cdb-123">Recuperar la identidad de Windows</span><span class="sxs-lookup"><span data-stu-id="e7cdb-123">Retrieving Windows Identity</span></span>  
 <span data-ttu-id="e7cdb-124">El código CLR que se ejecuta dentro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siempre se invoca en el contexto de la cuenta de proceso.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-124">CLR code executing inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is always invoked in the context of the process account.</span></span> <span data-ttu-id="e7cdb-125">Si el código debe realizar determinadas acciones utilizando la identidad del usuario que es el autor de la llamada, en lugar de la identidad del proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se debe obtener un token de suplantación a través de la propiedad `WindowsIdentity` del objeto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-125">If the code should perform certain actions using the identity of the calling user, instead of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process identity, then an impersonation token should be obtained through the `WindowsIdentity` property of the `SqlContext` object.</span></span> <span data-ttu-id="e7cdb-126">La propiedad `WindowsIdentity` devuelve una instancia de `WindowsIdentity` que representa la identidad en Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] del autor de la llamada, o bien, null si el cliente se autenticó utilizando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7cdb-126">The `WindowsIdentity` property returns a `WindowsIdentity` instance representing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows identity of the caller, or null if the client was authenticated using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e7cdb-127">Solo los ensamblados marcados con los permisos `EXTERNAL_ACCESS` o `UNSAFE` tienen acceso a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-127">Only assemblies marked with `EXTERNAL_ACCESS` or `UNSAFE` permissions can access this property.</span></span>  
  
 <span data-ttu-id="e7cdb-128">Después de obtener el objeto `WindowsIdentity`, los autores de la llamada pueden suplantar la cuenta del cliente y realizar acciones en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-128">After obtaining the `WindowsIdentity` object, callers can impersonate the client account and perform actions on their behalf.</span></span>  
  
 <span data-ttu-id="e7cdb-129">La identidad del autor de la llamada solo está disponible a través de `SqlContext.WindowsIdentity` si el cliente que inició la ejecución del procedimiento almacenado o función se conectó al servidor utilizando la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-129">The identity of the caller is only available through `SqlContext.WindowsIdentity` if the client that initiated execution of the stored-procedure or function connected to the server using Windows Authentication.</span></span> <span data-ttu-id="e7cdb-130">Si en su lugar se utilizara la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esta propiedad sería NULL y el código no podría suplantar al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-130">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication was used instead, this property is null and the code is unable to impersonate the caller.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e7cdb-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7cdb-131">Example</span></span>  
 <span data-ttu-id="e7cdb-132">En el ejemplo siguiente, se muestra cómo obtener la identidad de Windows del cliente de la llamada y suplantarla.</span><span class="sxs-lookup"><span data-stu-id="e7cdb-132">The following example shows how to get the Windows identity of the calling client and impersonate the client.</span></span>  
  
 <span data-ttu-id="e7cdb-133">C#</span><span class="sxs-lookup"><span data-stu-id="e7cdb-133">C#</span></span>  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void WindowsIDTestProc()  
{  
    WindowsIdentity clientId = null;  
    WindowsImpersonationContext impersonatedUser = null;  
  
    // Get the client ID.  
    clientId = SqlContext.WindowsIdentity;  
  
    // This outer try block is used to thwart exception filter   
    // attacks which would prevent the inner finally   
    // block from executing and resetting the impersonation.  
    try  
    {  
        try  
        {  
            impersonatedUser = clientId.Impersonate();  
            if (impersonatedUser != null)  
            {  
                // Perform some action using impersonation.  
            }  
        }  
        finally  
        {  
            // Undo impersonation.  
            if (impersonatedUser != null)  
                impersonatedUser.Undo();  
        }  
    }  
    catch  
    {  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="e7cdb-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7cdb-134">Visual Basic</span></span>  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  WindowsIDTestProcVB ()  
    Dim clientId As WindowsIdentity  
    Dim impersonatedUser As WindowsImpersonationContext  
  
    ' Get the client ID.  
    clientId = SqlContext.WindowsIdentity  
  
    ' This outer try block is used to thwart exception filter   
    ' attacks which would prevent the inner finally   
    ' block from executing and resetting the impersonation.  
  
    Try  
        Try  
  
            impersonatedUser = clientId.Impersonate()  
  
            If impersonatedUser IsNot Nothing Then  
                ' Perform some action using impersonation.  
            End If  
  
        Finally  
            ' Undo impersonation.  
            If impersonatedUser IsNot Nothing Then  
                impersonatedUser.Undo()  
            End If  
        End Try  
  
    Catch e As Exception  
  
        Throw e  
  
    End Try  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7cdb-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7cdb-135">See Also</span></span>  
 <span data-ttu-id="e7cdb-136">[SqlPipe (objeto)](sqlpipe-object.md) </span><span class="sxs-lookup"><span data-stu-id="e7cdb-136">[SqlPipe Object](sqlpipe-object.md) </span></span>  
 <span data-ttu-id="e7cdb-137">[Objeto SqlTriggerContext](sqltriggercontext-object.md) </span><span class="sxs-lookup"><span data-stu-id="e7cdb-137">[SqlTriggerContext Object](sqltriggercontext-object.md) </span></span>  
 <span data-ttu-id="e7cdb-138">[Desencadenadores CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e7cdb-138">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="e7cdb-139">Extensiones específicas en proceso de SQL Server a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e7cdb-139">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
