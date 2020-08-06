---
title: Valores de HOST_NAME | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663350"
---
# <a name="host_name-values"></a><span data-ttu-id="844a6-102">Valores de HOST_NAME</span><span class="sxs-lookup"><span data-stu-id="844a6-102">HOST_NAME Values</span></span>
  <span data-ttu-id="844a6-103">Las publicaciones de combinación con filtros con parámetros utilizan la función SUSER_SNAME() o la función HOST_NAME() para filtrar datos.</span><span class="sxs-lookup"><span data-stu-id="844a6-103">Merge publications with parameterized filters use the SUSER_SNAME() function and/or the HOST_NAME() function to filter data.</span></span> <span data-ttu-id="844a6-104">La función se especifica en el Asistente para nueva publicación o en el cuadro de diálogo **Propiedades de la publicación** .</span><span class="sxs-lookup"><span data-stu-id="844a6-104">The function is specified in the New Publication Wizard or the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="844a6-105">De forma predeterminada, la función HOST_NAME() devuelve el nombre del equipo que se conecta al publicador.</span><span class="sxs-lookup"><span data-stu-id="844a6-105">By default, the HOST_NAME() function returns the name of the computer connecting to the Publisher.</span></span> <span data-ttu-id="844a6-106">Cuando se utilizan filtros con parámetros, es normal reemplazar este valor suministrando otro en esta página del asistente.</span><span class="sxs-lookup"><span data-stu-id="844a6-106">When using parameterized filters, it is common to override this value by supplying a value on this page of the wizard.</span></span> <span data-ttu-id="844a6-107">A continuación, la función HOST_NAME() devuelve el valor que se ha especificado en vez del nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="844a6-107">The HOST_NAME() function then returns the value you specify rather than the name of the computer.</span></span> <span data-ttu-id="844a6-108">Para obtener más información, vea la sección sobre cómo reemplazar el valor de HOST_NAME() de [Filtros de fila con parámetros](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="844a6-108">For more information, see the "Overriding the HOST_NAME() Value" section of [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="844a6-109">Si reemplaza HOST_NAME(), todas las llamadas a la función HOST_NAME() devolverán el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="844a6-109">If you override HOST_NAME(), all calls to the HOST_NAME() function will return the value you specify.</span></span> <span data-ttu-id="844a6-110">Asegúrese de que otras aplicaciones no dependen de HOST_NAME() al devolver el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="844a6-110">Ensure that other applications are not depending on HOST_NAME() returning the computer name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="844a6-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="844a6-111">Options</span></span>  
 <span data-ttu-id="844a6-112">**Propiedades de la suscripción**</span><span class="sxs-lookup"><span data-stu-id="844a6-112">**Subscription properties**</span></span>  
 <span data-ttu-id="844a6-113">Escriba un valor para cada suscriptor en la columna **Valor de HOST_NAME** o acepte el valor predeterminado, que es el nombre del equipo suscriptor.</span><span class="sxs-lookup"><span data-stu-id="844a6-113">Enter a value for each Subscriber in the **HOST_NAME Value** column or accept the default, which is the name of the Subscriber computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844a6-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="844a6-114">See Also</span></span>  
 <span data-ttu-id="844a6-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="844a6-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="844a6-116">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="844a6-116">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="844a6-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md)  (Ver y modificar las propiedades de una suscripción de extracción)</span><span class="sxs-lookup"><span data-stu-id="844a6-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="844a6-118">[Ver y modificar las propiedades de una suscripción de inserción](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="844a6-118">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="844a6-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="844a6-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span></span>  
 [<span data-ttu-id="844a6-120">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="844a6-120">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
