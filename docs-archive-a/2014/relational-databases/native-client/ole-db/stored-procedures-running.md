---
title: Ejecución de procedimientos almacenados (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6ce951f343002feea5aa793d0cc2092422b819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748729"
---
# <a name="running-stored-procedures-ole-db"></a><span data-ttu-id="7d7ac-102">Ejecutar procedimientos almacenados (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7d7ac-102">Running Stored Procedures (OLE DB)</span></span>
  <span data-ttu-id="7d7ac-103">Cuando se ejecutan instrucciones, llamar a un procedimiento almacenado en el origen de datos (en lugar de ejecutar o preparar directamente una instrucción en la aplicación cliente) puede proporcionar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d7ac-103">When executing statements, calling a stored procedure on the data source (instead of executing or preparing a statement in the client application directly) can provide:</span></span>  
  
-   <span data-ttu-id="7d7ac-104">Mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-104">Higher performance.</span></span>  
  
-   <span data-ttu-id="7d7ac-105">Sobrecarga de red reducida.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-105">Reduced network overhead.</span></span>  
  
-   <span data-ttu-id="7d7ac-106">Mejor coherencia</span><span class="sxs-lookup"><span data-stu-id="7d7ac-106">Better consistency.</span></span>  
  
-   <span data-ttu-id="7d7ac-107">Mayor exactitud</span><span class="sxs-lookup"><span data-stu-id="7d7ac-107">Better accuracy.</span></span>  
  
-   <span data-ttu-id="7d7ac-108">Función agregada.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-108">Added functionality.</span></span>  
  
 <span data-ttu-id="7d7ac-109">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite tres de los mecanismos que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] los procedimientos almacenados usan para devolver datos:</span><span class="sxs-lookup"><span data-stu-id="7d7ac-109">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports three of the mechanisms that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures use to return data:</span></span>  
  
-   <span data-ttu-id="7d7ac-110">Cada instrucción SELECT del procedimiento genera un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-110">Every SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="7d7ac-111">El procedimiento puede devolver datos mediante parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-111">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="7d7ac-112">El procedimiento puede tener un código de retorno de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-112">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="7d7ac-113">La aplicación debe ser capaz de manejar todos estos resultados de los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-113">The application must be able to handle all of these outputs from stored procedures.</span></span>  
  
 <span data-ttu-id="7d7ac-114">Diferentes proveedores OLE DB devuelven parámetros de salida y valores devueltos en diferentes momentos durante el procesamiento de los resultados.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-114">Different OLE DB providers return output parameters and return values at different times during result processing.</span></span> <span data-ttu-id="7d7ac-115">En el caso del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, los parámetros de salida y los códigos de retorno no se suministran hasta que el consumidor haya recuperado o cancelado los conjuntos de resultados devueltos por el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-115">In case of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the output parameters and return codes are not supplied until after the consumer has retrieved or canceled the result sets returned by the stored procedure.</span></span> <span data-ttu-id="7d7ac-116">Los códigos de retorno y los parámetros de salida se devuelven en el último paquete TDS del servidor.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-116">The return codes and the output parameters are returned in the last TDS packet from the server.</span></span>  
  
 <span data-ttu-id="7d7ac-117">Los proveedores usan la propiedad DBPROP_OUTPUTPARAMETERAVAILABILITY para notificar cuando devuelve parámetros de salida y valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-117">Providers use the DBPROP_OUTPUTPARAMETERAVAILABILITY property to report when it returns output parameters and return values.</span></span> <span data-ttu-id="7d7ac-118">Esta propiedad se encuentra en el conjunto de propiedades DBPROPSET_DATASOURCEINFO.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-118">This property is in the DBPROPSET_DATASOURCEINFO property set.</span></span>  
  
 <span data-ttu-id="7d7ac-119">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client establece la propiedad DBPROP_OUTPUTPARAMETERAVAILABILITY en DBPROPVAL_OA_ATROWRELEASE para indicar que no se devuelven los códigos de retorno y los parámetros de salida hasta que se procesa o libera el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7d7ac-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets the DBPROP_OUTPUTPARAMETERAVAILABILITY property to DBPROPVAL_OA_ATROWRELEASE to indicate that return codes and output parameters are not returned until the result set is processed or released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7ac-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d7ac-120">See Also</span></span>  
 [<span data-ttu-id="7d7ac-121">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="7d7ac-121">Stored Procedures</span></span>](stored-procedures.md)  
  
  
