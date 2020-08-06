---
title: 'Tutorial: Introducción al motor de base de datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorials [connecting]
- tutorials [Database Engine]
- unable to connect [SQL Server]
- failure to connect [SQL Server]
- connecting tutorial [SQL Server]
ms.assetid: 655e709b-346b-469c-bddc-a5a0238d07e0
author: rothja
ms.author: jroth
ms.openlocfilehash: aaa1fb21c026d064c2b14db73aadc2b82e9c15d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676905"
---
# <a name="tutorial-getting-started-with-the-database-engine"></a><span data-ttu-id="6456e-102">Tutorial: Introducción al motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="6456e-102">Tutorial: Getting Started with the Database Engine</span></span>
  <span data-ttu-id="6456e-103">Éste es el tutorial de introducción a [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6456e-103">Welcome to the Getting Started with the [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorial.</span></span> <span data-ttu-id="6456e-104">Este tutorial está destinado a usuarios nuevos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que hayan instalado [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6456e-104">This tutorial is intended for users who are new to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and who have installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="6456e-105">Este breve tutorial le ayuda a comenzar a usar [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6456e-105">This brief tutorial helps you get started using the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="6456e-106">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="6456e-106">What You Will Learn</span></span>  
 <span data-ttu-id="6456e-107">Este tutorial le muestra cómo conectarse a [!INCLUDE[ssDE](../includes/ssde-md.md)] con [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , tanto en el equipo local como desde otro equipo.</span><span class="sxs-lookup"><span data-stu-id="6456e-107">This tutorial shows you how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on both the local computer and from another computer.</span></span>  
  
 <span data-ttu-id="6456e-108">El tutorial está compuesto por dos lecciones:</span><span class="sxs-lookup"><span data-stu-id="6456e-108">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="6456e-109">Lección 1: conectarse al motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="6456e-109">Lesson 1: Connecting to the Database Engine</span></span>](lesson-1-connecting-to-the-database-engine.md)  
 <span data-ttu-id="6456e-110">En esta lección aprenderá a conectarse a [!INCLUDE[ssDE](../includes/ssde-md.md)] y a permitir que otras personas se conecten.</span><span class="sxs-lookup"><span data-stu-id="6456e-110">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] and enable additional people to connect.</span></span>  
  
 [<span data-ttu-id="6456e-111">Lección 2: Conectarse desde otro equipo</span><span class="sxs-lookup"><span data-stu-id="6456e-111">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
 <span data-ttu-id="6456e-112">En esta lección aprenderá a conectarse a [!INCLUDE[ssDE](../includes/ssde-md.md)] desde un segundo equipo, incluidas la habilitación de protocolos, la configuración de puertos y la configuración de opciones del firewall.</span><span class="sxs-lookup"><span data-stu-id="6456e-112">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from a second computer, including enabling protocols, configuring ports, and configuring firewall settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6456e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6456e-113">Requirements</span></span>  
 <span data-ttu-id="6456e-114">Este tutorial no tiene requisitos previos en cuanto a conocimientos.</span><span class="sxs-lookup"><span data-stu-id="6456e-114">This tutorial has no knowledge prerequisites.</span></span>  
  
 <span data-ttu-id="6456e-115">Para usar este tutorial, debe tener el software siguiente instalado en el sistema:</span><span class="sxs-lookup"><span data-stu-id="6456e-115">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="6456e-116">.</span><span class="sxs-lookup"><span data-stu-id="6456e-116">.</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] <span data-ttu-id="6456e-117">se puede instalar ejecutando el programa de instalación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o descargando e instalando desde el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?LinkId=144346).</span><span class="sxs-lookup"><span data-stu-id="6456e-117">can be installed by running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup or by downloading and installing from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6456e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6456e-118">See Also</span></span>  
 [<span data-ttu-id="6456e-119">Tutorial: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6456e-119">Tutorial: SQL Server Management Studio</span></span>](../ssms/tutorials/tutorial-sql-server-management-studio.md)  
  
  
