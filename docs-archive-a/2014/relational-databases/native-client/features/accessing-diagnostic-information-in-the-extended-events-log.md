---
title: Obtener acceso a información de diagnóstico en el registro de eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: aaa180c2-5e1a-4534-a125-507c647186ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 5148683d464f06e8a4f52cc924baaacac9102b12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745264"
---
# <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="3dd3a-102">Obtener acceso a información de diagnóstico en el registro de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="3dd3a-102">Accessing Diagnostic Information in the Extended Events Log</span></span>
  <span data-ttu-id="3dd3a-103">A partir de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] el seguimiento de acceso a datos y de Native Client ([seguimiento de acceso a datos](https://go.microsoft.com/fwlink/?LinkId=125805)) se ha actualizado para facilitar la obtención de información de diagnóstico sobre los errores de conexión desde el búfer de anillo de conectividad y la información de rendimiento de la aplicación desde el registro de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data access tracing ([Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805)) have been updated to make it easier to get diagnostic information about connection failures from the connectivity ring buffer and application performance information from the extended events log.</span></span>  
  
 <span data-ttu-id="3dd3a-104">Para obtener información sobre la lectura del registro de eventos extendidos, vea [Ver datos de sesión de evento](../../../database-engine/view-event-session-data.md).</span><span class="sxs-lookup"><span data-stu-id="3dd3a-104">For information about reading the extended events log, see [View Event Session Data](../../../database-engine/view-event-session-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3dd3a-105">Esta función está dirigida únicamente a la solución de problemas y al diagnóstico, además es posible que no sea adecuada para fines de auditoría o seguridad.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-105">This feature is intended only for troubleshooting and diagnostic purposes and may not be suitable for auditing or security purposes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dd3a-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3dd3a-106">Remarks</span></span>  
 <span data-ttu-id="3dd3a-107">Para las operaciones de conexión, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client enviará un identificador de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-107">For connection operations, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will send a client connection ID.</span></span> <span data-ttu-id="3dd3a-108">Si se produce un error en la conexión, puede tener acceso al búfer de anillo de conectividad ([solución de problemas de conectividad en SQL Server 2008 con el búfer de anillo de conectividad](https://go.microsoft.com/fwlink/?LinkId=207752)) y buscar el `ClientConnectionID` campo y obtener información de diagnóstico sobre el error de conexión.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-108">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](https://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="3dd3a-109">Los identificadores de conexión del cliente se registran en el búfer de anillo únicamente si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-109">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="3dd3a-110">(Si se produce un error en una conexión antes de enviar el paquete de inicio de sesión previo, no se generará un identificador de conexión del cliente). El identificador de conexión del cliente es un GUID de 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-110">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="3dd3a-111">Asimismo, puede buscar el identificador de conexión del cliente en el destino de salida de eventos extendidos, si se agrega la acción `client_connection_id` a los eventos de una sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-111">You can also find the client connection ID in the extended events output target, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="3dd3a-112">Puede habilitar el seguimiento de acceso a datos, volver a ejecutar el comando de conexión y observar el campo de `ClientConnectionID` en el seguimiento de acceso a datos de una operación que no se realizó correctamente, si necesita asistencia adicional de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-112">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace for a failed operation, if you need further diagnostic assistance.</span></span>  
  
 <span data-ttu-id="3dd3a-113">Si usa ODBC en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client y una conexión se realiza correctamente, puede obtener el identificador de conexión de cliente mediante el `SQL_COPT_SS_CLIENT_CONNECTION_ID` atributo con [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="3dd3a-113">If you are using ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and a connection succeeds, you can get the client connection ID by using the `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribute with [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="3dd3a-114">Native Client también envía un identificador de actividad específico para cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-114">Native Client also sends a thread-specific activity ID.</span></span> <span data-ttu-id="3dd3a-115">El identificador de actividad se captura en las sesiones de eventos extendidos si las sesiones se inician con la opción TRACK_CAUSAILITY habilitada.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-115">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="3dd3a-116">Con respecto a los problemas de rendimiento con una conexión activa, puede obtener el identificador de actividad a partir del seguimiento de acceso a datos del cliente (campo `ActivityID`) y, posteriormente, buscar el identificador de actividad en la salida de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-116">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="3dd3a-117">El identificador de actividad en los eventos extendidos es un GUID de 16 bytes (no es el mismo que el GUID para el identificador de conexión del cliente) anexado a un número de secuencia de cuatro bytes.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-117">The activity ID in the extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="3dd3a-118">El número de secuencia representa el orden de una solicitud en un subproceso e indica el orden relativo del lote, así como las instrucciones RPC para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-118">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="3dd3a-119">`ActivityID` se envía opcionalmente para las instrucciones por lotes de SQL y solicitudes RPC cuando el seguimiento de acceso a datos se habilita y el bit décimo octavo de la palabra de configuración del seguimiento de acceso a datos se establece en ON.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-119">The `ActivityID` is optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="3dd3a-120">A continuación, se aporta un ejemplo que utiliza [!INCLUDE[tsql](../../../includes/tsql-md.md)] para iniciar una sesión de eventos extendidos que se va a almacenar en un búfer de anillo y que registrará el identificador de actividad que se envía desde un cliente en operaciones de RPC y por lotes.</span><span class="sxs-lookup"><span data-stu-id="3dd3a-120">The following is a sample that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
  
```  
  
## <a name="control-file"></a><span data-ttu-id="3dd3a-121">Archivo de control</span><span class="sxs-lookup"><span data-stu-id="3dd3a-121">Control File</span></span>  
 <span data-ttu-id="3dd3a-122">En [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], el contenido del archivo de control de SQL Server Native Client (ctrl.guid.snac11) es:</span><span class="sxs-lookup"><span data-stu-id="3dd3a-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client control file (ctrl.guid.snac11) is:</span></span>  
  
```  
{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}  0x00000000  0   MSDADIAG.ETW  
{2DA81B52-908E-7DB6-EF81-76856BB47C4F}  0xFFFFFFFF  0   SQLNCLI11.1  
```  
  
## <a name="mof-file"></a><span data-ttu-id="3dd3a-123">Archivo MOF</span><span class="sxs-lookup"><span data-stu-id="3dd3a-123">MOF File</span></span>  
 <span data-ttu-id="3dd3a-124">En [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], el contenido del archivo MOF de SQL Server Native Client es:</span><span class="sxs-lookup"><span data-stu-id="3dd3a-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client mof file is:</span></span>  
  
```  
#pragma classflags("forceupdate")  
#pragma namespace ("\\\\.\\Root\\WMI")  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  MSDADIAG.ETW  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F3-3CC6-0B9C-6651-9649CCE5C752}"),  
 DisplayName("msdadiag"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace : Bid2Etw_MSDADIAG_ETW  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextA : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextW : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  SQLNCLI11.1  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B52-908E-7DB6-EF81-76856BB47C4F}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1 : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B53-908E-7DB6-EF81-76856BB47C4F}"),  
 DisplayName("SQLNCLI11.1"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace : Bid2Etw_SQLNCLI11_1  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextA : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextW : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dd3a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dd3a-125">See Also</span></span>  
 [<span data-ttu-id="3dd3a-126">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="3dd3a-126">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
