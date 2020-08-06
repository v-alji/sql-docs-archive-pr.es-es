---
title: Propiedades de Agente SQL Server (página General) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676302"
---
# <a name="sql-server-agent-properties-general-page"></a><span data-ttu-id="69d53-102">Propiedades de Agente SQL Server (página General)</span><span class="sxs-lookup"><span data-stu-id="69d53-102">SQL Server Agent Properties (General Page)</span></span>
  <span data-ttu-id="69d53-103">Utilice esta página para ver y modificar las propiedades generales del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio del agente.</span><span class="sxs-lookup"><span data-stu-id="69d53-103">Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="69d53-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="69d53-104">Options</span></span>  
 <span data-ttu-id="69d53-105">**Estado de servicio**</span><span class="sxs-lookup"><span data-stu-id="69d53-105">**Service state**</span></span>  
 <span data-ttu-id="69d53-106">Muestra el estado actual del servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69d53-106">Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
 <span data-ttu-id="69d53-107">**Reiniciar SQL Server si se detiene inesperadamente**</span><span class="sxs-lookup"><span data-stu-id="69d53-107">**Auto restart SQL Server if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69d53-108">El Agente reinicia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se detiene de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="69d53-108">Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stops unexpectedly.</span></span>  
  
 <span data-ttu-id="69d53-109">**Reiniciar el Agente SQL Server automáticamente si se detiene inesperadamente**</span><span class="sxs-lookup"><span data-stu-id="69d53-109">**Auto restart SQL Server Agent if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69d53-110">reinicia el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se detiene de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="69d53-110">restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stops unexpectedly.</span></span>  
  
 <span data-ttu-id="69d53-111">**Extensión**</span><span class="sxs-lookup"><span data-stu-id="69d53-111">**Filename**</span></span>  
 <span data-ttu-id="69d53-112">Especifica el nombre de archivo del registro de errores.</span><span class="sxs-lookup"><span data-stu-id="69d53-112">Specify the file name for the error log.</span></span>  
  
 <span data-ttu-id="69d53-113">**...**</span><span class="sxs-lookup"><span data-stu-id="69d53-113">**...**</span></span>  
 <span data-ttu-id="69d53-114">Permite buscar el archivo del registro de errores.</span><span class="sxs-lookup"><span data-stu-id="69d53-114">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="69d53-115">**Incluir mensajes de seguimiento de ejecución**</span><span class="sxs-lookup"><span data-stu-id="69d53-115">**Include execution trace messages**</span></span>  
 <span data-ttu-id="69d53-116">Incluye mensajes de seguimiento de ejecución en el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="69d53-116">Includes execution trace messages in the error log.</span></span> <span data-ttu-id="69d53-117">Los mensajes de seguimiento proporcionan información detallada sobre la operación del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69d53-117">Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operation.</span></span> <span data-ttu-id="69d53-118">Por tanto, el archivo de registro requiere más espacio en disco cuando se selecciona esta opción.</span><span class="sxs-lookup"><span data-stu-id="69d53-118">Therefore, the log file requires more disk space when this option is selected.</span></span> <span data-ttu-id="69d53-119">Solo se debe seleccionar si se intenta solucionar un problema que puede estar relacionado con el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69d53-119">This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="69d53-120">**Escribir archivo OEM**</span><span class="sxs-lookup"><span data-stu-id="69d53-120">**Write OEM file**</span></span>  
 <span data-ttu-id="69d53-121">Escribe el archivo de registro de errores como un archivo no Unicode.</span><span class="sxs-lookup"><span data-stu-id="69d53-121">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="69d53-122">De esta forma, se reduce el espacio en disco que utiliza el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="69d53-122">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="69d53-123">Sin embargo, si se habilita esta opción, puede resultar más difícil leer los mensajes que incluyen datos Unicode.</span><span class="sxs-lookup"><span data-stu-id="69d53-123">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="69d53-124">**Destinatario de NET SEND**</span><span class="sxs-lookup"><span data-stu-id="69d53-124">**Net send recipient**</span></span>  
 <span data-ttu-id="69d53-125">Escribe el nombre de un operador que recibirá una notificación mediante NET SEND de los mensajes que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escribe en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="69d53-125">Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d53-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69d53-126">See Also</span></span>  
 <span data-ttu-id="69d53-127">[Operadores](operators.md) </span><span class="sxs-lookup"><span data-stu-id="69d53-127">[Operators](operators.md) </span></span>  
 [<span data-ttu-id="69d53-128">Registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="69d53-128">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
