---
title: Entornos multiusuario (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- users [SQL Server], multiuser environments
- conflict resolution [Visual Database Tools]
- multiple users making database changes
- multiuser environments [Visual Database Tools]
- database modifications [SQL Server]
- version control [Visual Database Tools]
- Visual Database Tools [SQL Server], multiuser environments
ms.assetid: 330bd48c-9427-4967-b58e-b7c492d5ee36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2e219ecda25f477aa459de674a43d9c2360376ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670738"
---
# <a name="multiuser-environments-visual-database-tools"></a><span data-ttu-id="deacf-102">Entornos multiusuario (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="deacf-102">Multiuser Environments (Visual Database Tools)</span></span>
  <span data-ttu-id="deacf-103">Un entorno multiusuario es un entorno al que otros usuarios pueden conectarse y en el que pueden realizar cambios en la misma base de datos en la que usted está trabajando.</span><span class="sxs-lookup"><span data-stu-id="deacf-103">A multiuser environment is one in which other users can connect and make changes to the same database that you are working with.</span></span> <span data-ttu-id="deacf-104">Como resultado, es posible que varios usuarios estén trabajando con los mismos objetos de base de datos a la vez.</span><span class="sxs-lookup"><span data-stu-id="deacf-104">As a result, several users might be working with the same database objects at the same time.</span></span> <span data-ttu-id="deacf-105">De este modo, en un entorno multiusuario es posible que la base de datos se vea afectada por los cambios realizados por otros usuarios mientras está trabajando y viceversa.</span><span class="sxs-lookup"><span data-stu-id="deacf-105">Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.</span></span>  
  
 <span data-ttu-id="deacf-106">Una cuestión clave al trabajar con bases de datos en un entorno multiusuario son los permisos de acceso.</span><span class="sxs-lookup"><span data-stu-id="deacf-106">A key issue when working with databases in a multiuser environment is access permissions.</span></span> <span data-ttu-id="deacf-107">Los permisos de que dispone para la base de datos determinan el alcance del trabajo que puede realizar con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="deacf-107">The permissions you have for the database determine the extent of the work you can do with the database.</span></span> <span data-ttu-id="deacf-108">Por ejemplo, para realizar cambios en objetos en una base de datos, debe disponer de los permisos de escritura apropiados para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="deacf-108">For example, to make changes to objects in a database, you must have the appropriate write permissions for the database.</span></span> <span data-ttu-id="deacf-109">Para obtener más información acerca de los permisos en la base de datos, vea la documentación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="deacf-109">For more information about permissions in your database, see your database documentation.</span></span> <span data-ttu-id="deacf-110">Para más información, consulte [Permisos y Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="deacf-110">For more information see [Permissions and Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="deacf-111">Cuando guarda los cambios realizados en las tablas, el Diseñador de tablas comprueba que la base de datos no se ha modificado desde que se guardaron los cambios por última vez.</span><span class="sxs-lookup"><span data-stu-id="deacf-111">When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes.</span></span> <span data-ttu-id="deacf-112">Si otro usuario ha realizado cambios, se le notificará que se ha modificado la base de datos.</span><span class="sxs-lookup"><span data-stu-id="deacf-112">If another user has made changes, you will be notified that the database has been modified.</span></span> <span data-ttu-id="deacf-113">Es posible que necesite reconciliar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="deacf-113">You may need to reconcile these changes.</span></span> <span data-ttu-id="deacf-114">Para más información, consulte [Reconciliar los cambios realizados por varios usuarios &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="deacf-114">For more information, see [Reconcile Changes Made by Multiple Users &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="deacf-115">En un entorno multiusuario debe tenerse en cuenta consideraciones especiales para impedir que se produzcan conflictos en los cambios.</span><span class="sxs-lookup"><span data-stu-id="deacf-115">In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes.</span></span> <span data-ttu-id="deacf-116">Para más información, consulte [Problemas de evolución de bases de datos &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="deacf-116">For more information, see [Issues of Database Evolution &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="deacf-117">Un modo de evitar problemas es trabajar con una copia de la base de datos, como una base de datos de prueba, cuando realiza los cambios; a continuación, puede crear un script y ejecutarlo para que aplique estos cambios en la base de datos original después de solucionar los conflictos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="deacf-117">One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline.</span></span> <span data-ttu-id="deacf-118">Para más información, consulte [Bases de datos de desarrollo, pruebas y producción &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="deacf-118">For more information see [Development, Test, and Production Databases &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span></span>  
  
  
