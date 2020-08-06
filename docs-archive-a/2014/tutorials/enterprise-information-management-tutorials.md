---
title: Tutoriales de administración de información empresarial | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8745dc80-193d-4de0-9f17-ba648ab1e81c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8cde162479645ab13a6ae000cc46e42e3c10e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675077"
---
# <a name="enterprise-information-management-tutorials"></a><span data-ttu-id="1fa88-102">Tutoriales de Administración de información empresarial</span><span class="sxs-lookup"><span data-stu-id="1fa88-102">Enterprise Information Management Tutorials</span></span>
  <span data-ttu-id="1fa88-103">Esta sección contiene tutoriales sobre la administración de información en una empresa mediante las tecnologías de Administración de información empresarial (EIM) incluidas en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fa88-103">This section contains tutorials for managing information in an enterprise by using Enterprise Information Management (EIM) technologies that are included in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span> <span data-ttu-id="1fa88-104">Administración de información empresarial (EIM) de la empresa proporciona una cartera de soluciones que permiten a las organizaciones confiar en la credibilidad y la coherencia de sus datos para poder tomar decisiones empresariales críticas.</span><span class="sxs-lookup"><span data-stu-id="1fa88-104">Enterprise Integration Management (EIM) provides a portfolio of solutions that enable organizations to trust the credibility and consistency of their data so they can make critical business decisions.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="1fa88-105">dispone de las siguientes tecnologías que le ayudan a implementar soluciones de EIM en la empresa.</span><span class="sxs-lookup"><span data-stu-id="1fa88-105">has the following technologies that help you implement EIM solutions in your enterprise.</span></span>  
  
-   <span data-ttu-id="1fa88-106">SQL Server Integration Services (SSIS).</span><span class="sxs-lookup"><span data-stu-id="1fa88-106">SQL Server Integration Services (SSIS).</span></span> <span data-ttu-id="1fa88-107">SSIS proporciona una plataforma extensible y eficaz para la integración de datos procedentes de diversos orígenes en una solución completa de extracción, transformación y carga (ETL) que admite flujos de trabajo empresariales, un almacenamiento de datos o administración de datos maestros.</span><span class="sxs-lookup"><span data-stu-id="1fa88-107">SSIS provides a powerful, extensible platform for integrating data from various sources in a comprehensive extract, transform, and load (ETL) solution that supports business workflows, a data warehouse, or master data management.</span></span>  
  
-   <span data-ttu-id="1fa88-108">SQL Server Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="1fa88-108">SQL Server Data Quality Services (DQS).</span></span> <span data-ttu-id="1fa88-109">DQS permite limpiar, buscar coincidencias, normalizar y enriquecer los datos, de forma que pueda confiar en la información para Business Intelligence, un almacenamiento de datos y cargas de trabajo de procesamiento de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1fa88-109">DQS enables you to cleanse, match, standardize, and enrich data, so you can deliver trusted information for business intelligence, a data warehouse, and transaction processing workloads.</span></span>  
  
-   <span data-ttu-id="1fa88-110">SQL Server Master Data Services (MDS).</span><span class="sxs-lookup"><span data-stu-id="1fa88-110">SQL Server Master Data Services (MDS).</span></span> <span data-ttu-id="1fa88-111">MDS proporciona un concentrador central de datos que garantiza que la integridad de la información y la coherencia de los datos son constantes en las distintas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1fa88-111">MDS provides a central data hub that ensures that the integrity of information and consistency of data is constant across different applications.</span></span>  
  
 [<span data-ttu-id="1fa88-112">Administración de información empresarial con SSIS, MDS y DQS juntos &#91;tutorial&#93;</span><span class="sxs-lookup"><span data-stu-id="1fa88-112">Enterprise Information Management using SSIS, MDS, and DQS Together &#91;Tutorial&#93;</span></span>](../../2014/tutorials/enterprise-information-management-using-ssis-mds-and-dqs-together-[tutorial].md)  
 <span data-ttu-id="1fa88-113">En este tutorial, aprenderá a usar conjuntamente SSIS, MDS y DQS para implementar una solución de ejemplo de Administración de información empresaria (EIM).</span><span class="sxs-lookup"><span data-stu-id="1fa88-113">In this tutorial, you learn how to use SSIS, MDS, and DQS together to implement a sample Enterprise Information Management (EIM) solution.</span></span> <span data-ttu-id="1fa88-114">Primero usará DQS para crear una base de conocimiento con los datos de proveedor (metadatos), limpiar los datos de un archivo de Excel según la base de conocimiento, y buscar coincidencias en los datos para identificar y quitar duplicados en los datos.</span><span class="sxs-lookup"><span data-stu-id="1fa88-114">First, you use DQS to create a knowledgebase with the knowledge about the supplier data (metadata), cleanse the data in an Excel file against the knowledge base, and match the data to identify and remove duplicates in the data.</span></span> <span data-ttu-id="1fa88-115">Después usará el complemento MDS para Excel con el fin de cargar los datos limpios y coincidentes en MDS.</span><span class="sxs-lookup"><span data-stu-id="1fa88-115">Next, you use the MDS Add-in for Excel to upload the cleansed and matched data to MDS.</span></span> <span data-ttu-id="1fa88-116">A continuación, automatizará todo el proceso mediante una solución de SSIS.</span><span class="sxs-lookup"><span data-stu-id="1fa88-116">Then, you automate the whole process by using an SSIS solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa88-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fa88-117">See Also</span></span>  
 [<span data-ttu-id="1fa88-118">Administración de información empresarial: Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="1fa88-118">Enterprise Information Management - Microsoft SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=270871)  
  
  
