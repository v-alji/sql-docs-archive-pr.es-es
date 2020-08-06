---
title: Configurar registros de errores del Agente SQL Server (página General) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.configure.f1
ms.assetid: e08de622-6f87-470c-aee0-b2d6cb6cca88
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd4c083ea7e7d220d5da20594079b7679c0bb724
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674538"
---
# <a name="configure-sql-server-agent-error-logs-general-page"></a><span data-ttu-id="ff4bd-102">Configurar registros de errores del Agente SQL Server (página General)</span><span class="sxs-lookup"><span data-stu-id="ff4bd-102">Configure SQL Server Agent Error Logs (General Page)</span></span>
  <span data-ttu-id="ff4bd-103">Utilice esta pantalla para ver y actualizar la configuración del registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff4bd-103">Use this screen to view and update settings for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logging.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff4bd-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="ff4bd-104">Options</span></span>  
 <span data-ttu-id="ff4bd-105">**Archivo de registro de errores**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-105">**Error log file**</span></span>  
 <span data-ttu-id="ff4bd-106">Especifique el archivo en el que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escribe los registros de errores.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-106">Specifies the file to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes error logs.</span></span>  
  
 <span data-ttu-id="ff4bd-107">**...**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-107">**...**</span></span>  
 <span data-ttu-id="ff4bd-108">Permite buscar el archivo del registro de errores.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-108">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="ff4bd-109">**Escribir registro de errores OEM**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-109">**Write OEM error log**</span></span>  
 <span data-ttu-id="ff4bd-110">Escribe el archivo de registro de errores como un archivo no Unicode.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-110">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="ff4bd-111">De esta forma, se reduce el espacio en disco que utiliza el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-111">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="ff4bd-112">Sin embargo, si se habilita esta opción, puede resultar más difícil leer los mensajes que incluyen datos Unicode.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-112">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="ff4bd-113">**Errores**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-113">**Errors**</span></span>  
 <span data-ttu-id="ff4bd-114">Solo escribe errores y mensajes informativos en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-114">Writes only errors and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="ff4bd-115">**Advertencias**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-115">**Warnings**</span></span>  
 <span data-ttu-id="ff4bd-116">Solo escribe advertencias y mensajes informativos en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-116">Writes only warnings and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="ff4bd-117">**Información**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-117">**Information**</span></span>  
 <span data-ttu-id="ff4bd-118">Solo escribe mensajes informativos en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ff4bd-118">Writes only informational messages to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4bd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff4bd-119">See Also</span></span>  
 [<span data-ttu-id="ff4bd-120">Registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff4bd-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
