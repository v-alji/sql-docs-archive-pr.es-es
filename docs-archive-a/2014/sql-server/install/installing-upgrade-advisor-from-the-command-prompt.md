---
title: Instalación del Asesor de actualizaciones desde el símbolo del sistema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0c5193f0b235b6d37170992d9d7ca9568b1f675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744980"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a><span data-ttu-id="cd583-102">Instalar el Asesor de actualizaciones desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="cd583-102">Installing Upgrade Advisor from the Command Prompt</span></span>
  <span data-ttu-id="cd583-103">Puede instalar el Asesor de actualizaciones mediante el Asistente para instalación o desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd583-103">You can install Upgrade Advisor either by using the Setup Wizard or from the command prompt.</span></span> <span data-ttu-id="cd583-104">Mediante el símbolo del sistema, podrá realizar instalaciones desatendidas y automatizadas.</span><span class="sxs-lookup"><span data-stu-id="cd583-104">By using the command prompt you can perform unattended and automated installations.</span></span>  
  
## <a name="installation-syntax"></a><span data-ttu-id="cd583-105">Sintaxis de la instalación</span><span class="sxs-lookup"><span data-stu-id="cd583-105">Installation Syntax</span></span>  
 <span data-ttu-id="cd583-106">La sintaxis básica para instalar el Asesor de actualizaciones desde el símbolo del sistema es como sigue:</span><span class="sxs-lookup"><span data-stu-id="cd583-106">The basic syntax for installing Upgrade Advisor from the command prompt is as follows:</span></span>  
  
 `SQLUA.msi [options]`  
  
 <span data-ttu-id="cd583-107">En la tabla siguiente se muestran las opciones más comunes.</span><span class="sxs-lookup"><span data-stu-id="cd583-107">The following table shows the most common options.</span></span>  
  
|<span data-ttu-id="cd583-108">Argumento</span><span class="sxs-lookup"><span data-stu-id="cd583-108">Argument</span></span>|<span data-ttu-id="cd583-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd583-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="cd583-110">/q [n&#124;b&#124;r&#124;f]</span><span class="sxs-lookup"><span data-stu-id="cd583-110">/q[n&#124;b&#124;r&#124;f]</span></span>|<span data-ttu-id="cd583-111">Establece el nivel de la interfaz de usuario (UI):</span><span class="sxs-lookup"><span data-stu-id="cd583-111">Sets user interface (UI) level:</span></span><br /><br /> <span data-ttu-id="cd583-112">n = sin interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="cd583-112">n = no UI</span></span><br /><br /> <span data-ttu-id="cd583-113">b = interfaz de usuario básica (solo progresos, sin interacción)</span><span class="sxs-lookup"><span data-stu-id="cd583-113">b = basic UI (progress only, no prompts)</span></span><br /><br /> <span data-ttu-id="cd583-114">r = interfaz de usuario reducida (cuadro de diálogo al final de la instalación)</span><span class="sxs-lookup"><span data-stu-id="cd583-114">r = reduced UI (dialog box at the end of installation)</span></span><br /><br /> <span data-ttu-id="cd583-115">f = interfaz de usuario completa</span><span class="sxs-lookup"><span data-stu-id="cd583-115">f = full UI</span></span>|  
|<span data-ttu-id="cd583-116">/L</span><span class="sxs-lookup"><span data-stu-id="cd583-116">/L</span></span>|<span data-ttu-id="cd583-117">Especifica las opciones del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="cd583-117">Specifies log file options.</span></span> <span data-ttu-id="cd583-118">Para registrar todos los mensajes en *log_file_name*, use **-L \* v**_log_file_name_.</span><span class="sxs-lookup"><span data-stu-id="cd583-118">To log all messages to *log_file_name*, use **-L\*v**_log_file_name_.</span></span> <span data-ttu-id="cd583-119">Para registrar solo los mensajes de error, use `-Le` *log_file_name*.</span><span class="sxs-lookup"><span data-stu-id="cd583-119">To log error messages only, use `-Le`*log_file_name*.</span></span>|  
|<span data-ttu-id="cd583-120">ADDLOCAL = ALL&#124; REMOVE = ALL&#124;REINSTALL = ALL</span><span class="sxs-lookup"><span data-stu-id="cd583-120">ADDLOCAL=ALL&#124; REMOVE=ALL&#124;REINSTALL=ALL</span></span>|<span data-ttu-id="cd583-121">Se usa para instalar (ADDLOCAL), quitar (REMOVE) o reinstalar (REINSTALL) el Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="cd583-121">Specifies to install (ADDLOCAL), remove (REMOVE), or reinstall (REINSTALL) Upgrade Advisor.</span></span>|  
|<span data-ttu-id="cd583-122">UAINSTALLDIR=ruta</span><span class="sxs-lookup"><span data-stu-id="cd583-122">UAINSTALLDIR=path</span></span>|<span data-ttu-id="cd583-123">Instala el Asesor de actualizaciones en la ubicación especificada por la ruta.</span><span class="sxs-lookup"><span data-stu-id="cd583-123">Installs Upgrade Advisor to the location specified by path.</span></span>|  
  
## <a name="installation-examples"></a><span data-ttu-id="cd583-124">Ejemplos de instalación</span><span class="sxs-lookup"><span data-stu-id="cd583-124">Installation Examples</span></span>  
 <span data-ttu-id="cd583-125">El ejemplo siguiente muestra cómo instalar el Asesor de actualizaciones utilizando el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cd583-125">The following example shows how to install Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="cd583-126">También puede utilizar el programa Msiexec para ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="cd583-126">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="cd583-127">Esto puede resultar útil si tiene que utilizar opciones de instalación adicionales.</span><span class="sxs-lookup"><span data-stu-id="cd583-127">This can be helpful if you have to use additional installation options.</span></span>  
  
## <a name="removal-examples"></a><span data-ttu-id="cd583-128">Ejemplos de eliminación</span><span class="sxs-lookup"><span data-stu-id="cd583-128">Removal Examples</span></span>  
 <span data-ttu-id="cd583-129">El ejemplo siguiente muestra cómo eliminar el Asesor de actualizaciones utilizando el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cd583-129">The following example shows how to remove Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 <span data-ttu-id="cd583-130">También puede utilizar el programa Msiexec para ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="cd583-130">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd583-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd583-131">See Also</span></span>  
 <span data-ttu-id="cd583-132">[Instalando el asesor de actualizaciones](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="cd583-132">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="cd583-133">Requisitos previos del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="cd583-133">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
