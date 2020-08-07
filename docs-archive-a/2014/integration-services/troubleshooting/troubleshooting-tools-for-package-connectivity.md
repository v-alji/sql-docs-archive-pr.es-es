---
title: Solución de problemas de conectividad de paquetes de herramientas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, troubleshooting
- SSIS packages, troubleshooting
- Integration Services, troubleshooting
- connectivity [Integration Services], troubleshooting
- errors [Integration Services], troubleshooting
- packages [Integration Services], troubleshooting
ms.assetid: 08a019f5-8ba7-4527-97c1-e9846d4022ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1baac9af5a30fdc0f5b15e8ac56eb5badacc0edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745895"
---
# <a name="troubleshooting-tools-package-connectivity"></a><span data-ttu-id="3675f-102">Herramientas para solucionar problemas de conectividad entre paquetes</span><span class="sxs-lookup"><span data-stu-id="3675f-102">Troubleshooting Tools Package Connectivity</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="3675f-103">incluye características y herramientas que pueden usarse para solucionar problemas de conectividad entre los paquetes y los orígenes de datos desde los que los paquetes extraen y cargan los datos.</span><span class="sxs-lookup"><span data-stu-id="3675f-103">includes features and tools that you can use to troubleshoot connectivity between packages and the data sources from which packages extract and load data.</span></span>  
  
## <a name="troubleshooting-issues-with-external-data-providers"></a><span data-ttu-id="3675f-104">Solucionar problemas de proveedores de datos externos</span><span class="sxs-lookup"><span data-stu-id="3675f-104">Troubleshooting Issues with External Data Providers</span></span>  
 <span data-ttu-id="3675f-105">Muchos de los errores de los paquetes se producen durante la interacción con proveedores de datos externos.</span><span class="sxs-lookup"><span data-stu-id="3675f-105">Many packages fail during interactions with external data providers.</span></span> <span data-ttu-id="3675f-106">Sin embargo, los mensajes que dichos proveedores devuelven a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no suelen proporcionar suficiente información como para comenzar a solucionar los problemas de interacción.</span><span class="sxs-lookup"><span data-stu-id="3675f-106">However, the messages that those providers return to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] frequently do not provide enough information to start troubleshooting the interaction.</span></span> <span data-ttu-id="3675f-107">Para cubrir esta necesidad de solucionar problemas, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluye mensajes de registro que puede utilizar para solucionar problemas relacionados con la interacción de un paquete con orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="3675f-107">To address this troubleshooting need, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes logging messages that you can use to troubleshoot a package's interaction with external data sources.</span></span>  
  
-   <span data-ttu-id="3675f-108">**Habilitar el registro de paquetes y seleccionar el evento Diagnostic del paquete para ver los mensajes de solución de problemas**.</span><span class="sxs-lookup"><span data-stu-id="3675f-108">**Enable logging and select the package's Diagnostic event to see the troubleshooting messages**.</span></span> <span data-ttu-id="3675f-109">Los siguientes componentes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] son capaces de escribir un mensaje en el registro antes y después de cada llamada a un proveedor de datos externo:</span><span class="sxs-lookup"><span data-stu-id="3675f-109">The following [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components are capable of writing a message to the log before and after every call to an external data provider:</span></span>  
  
    -   <span data-ttu-id="3675f-110">Administrador de conexiones OLE DB, origen de OLE DB y destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="3675f-110">OLE DB connection manager, OLE DB source, and OLE DB destination</span></span>  
  
    -   <span data-ttu-id="3675f-111">Administrador de conexiones [!INCLUDE[vstecado](../../includes/vstecado-md.md)] y origen de ADO NET</span><span class="sxs-lookup"><span data-stu-id="3675f-111">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and ADO NET source</span></span>  
  
    -   <span data-ttu-id="3675f-112">Tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="3675f-112">Execute SQL task</span></span>  
  
    -   <span data-ttu-id="3675f-113">Transformación Búsqueda, transformación Comando de OLE DB y transformación Dimensión variable lenta</span><span class="sxs-lookup"><span data-stu-id="3675f-113">Lookup transformation, OLE DB Command transformation, and Slowly Changing Dimension transformation</span></span>  
  
     <span data-ttu-id="3675f-114">Los mensajes de registro incluyen el nombre del método al que se llama.</span><span class="sxs-lookup"><span data-stu-id="3675f-114">The log messages include the name of the method being called.</span></span> <span data-ttu-id="3675f-115">Por ejemplo, estos mensajes de registro podrían incluir el método `Open` de un objeto `Connection` de OLE DB o el método `ExecuteNonQuery` de un objeto `Command`.</span><span class="sxs-lookup"><span data-stu-id="3675f-115">For example, these log messages might include the `Open` method of an OLE DB `Connection` object or the `ExecuteNonQuery` method of a `Command` object.</span></span> <span data-ttu-id="3675f-116">Los mensajes tienen el formato siguiente, donde '%1!s!'</span><span class="sxs-lookup"><span data-stu-id="3675f-116">The messages have the following format, where '%1!s!'</span></span> <span data-ttu-id="3675f-117">es un marcador de posición para la información de método:</span><span class="sxs-lookup"><span data-stu-id="3675f-117">is a placeholder for the method information:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: '%1!s!'.  
    ExternalRequest_post: '%1!s!'. The external request has completed.  
    ```  
  
     <span data-ttu-id="3675f-118">Para solucionar los problemas de interacción con el proveedor de datos externos, revise el registro para comprobar si cada mensaje "anterior" (`ExternalRequest_pre`) tiene un mensaje "posterior" correspondiente (`ExternalRequest_post`).</span><span class="sxs-lookup"><span data-stu-id="3675f-118">To troubleshoot the interaction with the external data provider, review the log to see whether every "before" message (`ExternalRequest_pre`) has a corresponding "after" message (`ExternalRequest_post`).</span></span> <span data-ttu-id="3675f-119">Si no hay un mensaje "posterior" correspondiente, podrá saber que el proveedor de datos externo no respondió tal y como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="3675f-119">If there is no corresponding "after" message, you know that the external data provider did not respond as expected.</span></span>  
  
     <span data-ttu-id="3675f-120">En el siguiente ejemplo se muestran algunas filas de ejemplo de un registro que incluye estos mensajes de registro:</span><span class="sxs-lookup"><span data-stu-id="3675f-120">The following example shows some sample rows from a log that contains these logging messages:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: 'ITransactionJoin::JoinTransaction'.  
    ExternalRequest_post: 'ITransactionJoin::JoinTransaction succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Open'.  
    ExternalRequest_post: 'IDbConnection.Open succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.CreateCommand'.  
    ExternalRequest_post: 'IDbConnection.CreateCommand finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbCommand.ExecuteReader'.  
    ExternalRequest_post: 'IDbCommand.ExecuteReader finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.GetSchemaTable'.  
    ExternalRequest_post: 'IDataReader.GetSchemaTable finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.Close'.  
    ExternalRequest_post: 'IDataReader.Close finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Close'.  
    ExternalRequest_post: 'IDbConnection.Close finished'. The external request has completed."  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3675f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3675f-121">See Also</span></span>  
 <span data-ttu-id="3675f-122">[Herramientas para solucionar problemas con el desarrollo de paquetes](troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="3675f-122">[Troubleshooting Tools for Package Development](troubleshooting-tools-for-package-development.md) </span></span>  
 [<span data-ttu-id="3675f-123">Herramientas para solucionar problemas de la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="3675f-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
