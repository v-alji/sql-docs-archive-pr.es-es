---
title: Instrucciones y limitaciones de SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
ms.assetid: fe433d30-90a1-421e-85c6-af13294dc18d
author: rothja
ms.author: jroth
ms.openlocfilehash: e020cbf0ac32e4c878b0b74b67e7c9c679d5d178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661879"
---
# <a name="guidelines-and-limitations-of-sqlxml-40"></a><span data-ttu-id="96750-102">Instrucciones y limitaciones de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="96750-102">Guidelines and Limitations of SQLXML 4.0</span></span>
  <span data-ttu-id="96750-103">Recuerde lo siguiente cuando trabaje con SQLXML 4.0:</span><span class="sxs-lookup"><span data-stu-id="96750-103">Remember the following when working with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="96750-104">El código XML devuelto como resultado de una consulta no se valida con el esquema de asignación que generó el código XML.</span><span class="sxs-lookup"><span data-stu-id="96750-104">XML returned as a query result is not validated against the mapping schema that generated the XML.</span></span>  
  
-   <span data-ttu-id="96750-105">SQLXML 4.0 incluye PROGID independientes y dependientes de la versión.</span><span class="sxs-lookup"><span data-stu-id="96750-105">SQLXML 4.0 includes version-independent and version-dependent PROGIDs.</span></span> <span data-ttu-id="96750-106">Se recomienda que todas las aplicaciones de producción utilicen PROGID dependientes de la versión.</span><span class="sxs-lookup"><span data-stu-id="96750-106">It is recommended that all production applications use version-dependent PROGIDs.</span></span> <span data-ttu-id="96750-107">Esto es especialmente importante porque SQLXML 4.0 no es totalmente compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="96750-107">This is especially important because SQLXML 4.0 is not fully backward compatible.</span></span> <span data-ttu-id="96750-108">El uso de PROGID dependientes de la versión impide que se produzcan errores de producción al instalar nuevas versiones.</span><span class="sxs-lookup"><span data-stu-id="96750-108">Using version dependent PROGIDs protects from possible production failures when you install newer releases.</span></span> <span data-ttu-id="96750-109">El comportamiento del programa puede cambiar de una versión a otra por una serie de motivos, como la corrección de errores, posibles cambios en el diseño, etc.</span><span class="sxs-lookup"><span data-stu-id="96750-109">From release to release, program behavior may change for a variety of reasons, such as bug fixes, possible design changes, and so on.</span></span> <span data-ttu-id="96750-110">El uso de PROGID dependientes de la versión impide que se produzcan errores inesperados al instalar nuevas versiones.</span><span class="sxs-lookup"><span data-stu-id="96750-110">Using version-dependent PROGIDs protects from unexpected failure when you install newer releases.</span></span> <span data-ttu-id="96750-111">Con los PROGID dependientes de la versión, al instalar una nueva versión, la aplicación seguirá funcionando sin errores.</span><span class="sxs-lookup"><span data-stu-id="96750-111">With version-dependent PROGIDs, when you install a newer release, your application will continue to work without failure.</span></span> <span data-ttu-id="96750-112">Si decide cambiar los PROGID dependientes de versiones anteriores y utilizar los PROGID dependientes de la última versión en una nueva versión, debe probar la aplicación antes de llevarla a producción.</span><span class="sxs-lookup"><span data-stu-id="96750-112">If you decide to change the previous version-dependent PROGIDs and use the recent version-dependent PROGIDs in a newer release, you must test your application before putting it into production.</span></span> <span data-ttu-id="96750-113">Por ejemplo, las aplicaciones que utilizan PROGID independientes de la versión podrían producir un error en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="96750-113">For example, applications using version-independent PROGIDs may fail in the following scenario:</span></span>  
  
     <span data-ttu-id="96750-114">Ejecuta una aplicación que utiliza SQLXML 4.0 y PROGID independientes de la versión y decide instalar otro programa de software.</span><span class="sxs-lookup"><span data-stu-id="96750-114">You are running an application that uses SQLXML 4.0 and version-independent PROGIDs, and you decide to install some other software program.</span></span> <span data-ttu-id="96750-115">Este programa podría instalar una versión anterior de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="96750-115">This program might install an earlier version of SQLXML.</span></span> <span data-ttu-id="96750-116">Se puede producir un error en la aplicación porque los PROGID independientes de la versión de la aplicación apuntarán ahora a la versión anterior de SQLXML, que puede o no puede tener la característica SQLXML que utiliza la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96750-116">Your application may fail because the version-independent PROGIDS in your application now point to the earlier version of SQLXML, which may or may not have the SQLXML feature that your application is using.</span></span>  
  
-   <span data-ttu-id="96750-117">Si por alguna razón no desea utilizar el proveedor SQLXMLOLEDB y, en su lugar, desea usar el proveedor SQLOLEDB para las características SQLXML, establezca la propiedad **versión de SQLXML** en "SQLXML. 4.0".</span><span class="sxs-lookup"><span data-stu-id="96750-117">If for any reason you don't want to use the SQLXMLOLEDB provider, and instead want to use the SQLOLEDB provider for SQLXML features, set the **SQLXML Version** property to "SQLXML.4.0".</span></span>  
  
  
