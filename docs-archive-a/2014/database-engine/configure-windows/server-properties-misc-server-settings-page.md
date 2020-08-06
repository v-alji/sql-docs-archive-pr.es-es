---
title: Propiedades del servidor (página Configuración adicional del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.miscserversettings.f1
ms.assetid: b170c066-30cd-42dd-8d34-aa129ea09551
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a82a787140141c3bfa7b18776328a813be9f41f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673890"
---
# <a name="server-properties-misc-server-settings-page"></a><span data-ttu-id="119af-102">Propiedades del servidor (página Configuración adicional del servidor)</span><span class="sxs-lookup"><span data-stu-id="119af-102">Server Properties (Misc Server Settings Page)</span></span>
  <span data-ttu-id="119af-103">Utilice esta página para ver o modificar la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="119af-103">Use this page to view or modify your server settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="119af-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="119af-104">Options</span></span>  
 <span data-ttu-id="119af-105">**Idioma predeterminado para el usuario**</span><span class="sxs-lookup"><span data-stu-id="119af-105">**Default language for users**</span></span>  
 <span data-ttu-id="119af-106">Especifica el idioma predeterminado de los nuevos inicios de sesión creados.</span><span class="sxs-lookup"><span data-stu-id="119af-106">Specifies the default language for all newly created logins.</span></span>  
  
 <span data-ttu-id="119af-107">**Permitir que los desencadenadores activen otros**</span><span class="sxs-lookup"><span data-stu-id="119af-107">**Allow triggers to fire other triggers**</span></span>  
 <span data-ttu-id="119af-108">Controla si un desencadenador puede realizar una acción que inicie otro desencadenador.</span><span class="sxs-lookup"><span data-stu-id="119af-108">Controls whether a trigger can perform an action that initiates another trigger.</span></span> <span data-ttu-id="119af-109">Cuando esta opción está desactivada, un desencadenador no puede activar otros desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="119af-109">When cleared, triggers cannot be fired by another trigger.</span></span> <span data-ttu-id="119af-110">Si está activada, un desencadenador puede activar otros desencadenadores, hasta un máximo de 32 niveles.</span><span class="sxs-lookup"><span data-stu-id="119af-110">When selected, triggers can be fired by other triggers to as many as 32 levels.</span></span>  
  
 <span data-ttu-id="119af-111">**Usar el regulador de consultas para evitar consultas que se ejecuten durante mucho tiempo**</span><span class="sxs-lookup"><span data-stu-id="119af-111">**Use query governor to prevent long-running queries**</span></span>  
 <span data-ttu-id="119af-112">Especifica un límite de tiempo para la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="119af-112">Specifies an upper limit on the time within which a query can run.</span></span> <span data-ttu-id="119af-113">El término costo de consultas hace referencia al tiempo estimado, en segundos, necesario para ejecutar una consulta en una configuración de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="119af-113">Query cost refers to the estimated elapsed time, in seconds, required to execute a query on a specific hardware configuration.</span></span> <span data-ttu-id="119af-114">De manera predeterminada, el regulador de consultas está desactivado y se pueden ejecutar todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="119af-114">By default, the query governor is turned off and all queries are allowed to run.</span></span> <span data-ttu-id="119af-115">Si esta opción está activada, debe indicar un límite de tiempo en el cuadro de texto que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="119af-115">If this option is selected, you must enter a time limit in the text box below.</span></span> <span data-ttu-id="119af-116">Si especifica un valor positivo distinto de cero, el regulador de consultas no permitirá la ejecución de ninguna consulta que tenga un costo estimado superior al valor especificado.</span><span class="sxs-lookup"><span data-stu-id="119af-116">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost exceeding that value.</span></span>  
  
 <span data-ttu-id="119af-117">**Interpretar un año de dos dígitos como un año entre**</span><span class="sxs-lookup"><span data-stu-id="119af-117">**Interpret a two-digit year as falling between**</span></span>  
 <span data-ttu-id="119af-118">Especifica el rango de fechas de 100 años para interpretar valores de año de dos dígitos.</span><span class="sxs-lookup"><span data-stu-id="119af-118">Specifies the 100-year date range for interpreting two-digit year values.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="119af-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpreta los valores de fecha de dos dígitos como una referencia al año que finaliza con estos dígitos y se encuentra dentro del rango especificado.</span><span class="sxs-lookup"><span data-stu-id="119af-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will interpret two-digit date values to refer to the year ending in those digits that falls within the specified range.</span></span>  
  
 <span data-ttu-id="119af-120">Establezca el año final en el cuadro de la derecha.</span><span class="sxs-lookup"><span data-stu-id="119af-120">Set the right box with the ending year.</span></span> <span data-ttu-id="119af-121">Cuando se guarda el año final, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muestra automáticamente el año inicial en el cuadro izquierdo.</span><span class="sxs-lookup"><span data-stu-id="119af-121">When the ending year is saved, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will automatically populate the left box with the beginning year.</span></span>  
  
 <span data-ttu-id="119af-122">**Valores configurados**</span><span class="sxs-lookup"><span data-stu-id="119af-122">**Configured Values**</span></span>  
 <span data-ttu-id="119af-123">Muestra los valores configurados para las opciones de este panel.</span><span class="sxs-lookup"><span data-stu-id="119af-123">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="119af-124">Si cambia estos valores, haga clic en **Valores actuales** para comprobar si los cambios han surtido efecto.</span><span class="sxs-lookup"><span data-stu-id="119af-124">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="119af-125">Si los cambios no han surtido efecto, debe reiniciarse la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="119af-125">If the changes have not taken effect, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restated first.</span></span>  
  
 <span data-ttu-id="119af-126">**Valores actuales**</span><span class="sxs-lookup"><span data-stu-id="119af-126">**Running Values**</span></span>  
 <span data-ttu-id="119af-127">Presenta los valores actuales de las opciones de este panel.</span><span class="sxs-lookup"><span data-stu-id="119af-127">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="119af-128">Estos valores son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="119af-128">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119af-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="119af-129">See Also</span></span>  
 [<span data-ttu-id="119af-130">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="119af-130">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
