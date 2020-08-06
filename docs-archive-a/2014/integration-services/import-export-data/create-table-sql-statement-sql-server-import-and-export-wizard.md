---
title: Instrucción Create Table de SQL (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createtablesql.f1
ms.assetid: 0d6f6b3b-d023-4770-a8a9-65b2977c8d05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3fc2054711708a27691f2d7219c33749f11b977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674933"
---
# <a name="create-table-sql-statement-sql-server-import-and-export-wizard"></a><span data-ttu-id="d6903-102">Instrucción Create Table de SQL (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d6903-102">Create Table SQL Statement (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="d6903-103">Utilice el cuadro de diálogo **instrucción CREATE TABLE de SQL** para ver la instrucción que se generó automáticamente o para modificarla para sus fines.</span><span class="sxs-lookup"><span data-stu-id="d6903-103">Use the **Create Table SQL Statement** dialog box to view the statement that was generated automatically, or to modify it for your purposes.</span></span> <span data-ttu-id="d6903-104">Si modifica esta instrucción, probablemente también deba realizar cambios asociados en la asignación de columnas y, en adelante, mantener la instrucción SQL modificada manualmente.</span><span class="sxs-lookup"><span data-stu-id="d6903-104">If you modify this statement, you may also have to make associated changes to column mapping, and you will have to maintain the edited SQL statement manually thereafter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="d6903-105">genera una instrucción CREATE TABLE predeterminada basada en el origen de datos conectado.</span><span class="sxs-lookup"><span data-stu-id="d6903-105">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="d6903-106">La instrucción predeterminada CREATE TABLE no incluirá el atributo FILESTREAM, aunque la tabla de origen tenga una columna con el atributo FILESTREAM declarado.</span><span class="sxs-lookup"><span data-stu-id="d6903-106">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="d6903-107">Para ejecutar un componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con el atributo FILESTREAM, implemente en primer lugar el almacenamiento de FILESTREAM en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="d6903-107">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="d6903-108">A continuación, agregue el atributo FILESTREAM a la instrucción CREATE TABLE en el cuadro de diálogo **Crear tabla** .</span><span class="sxs-lookup"><span data-stu-id="d6903-108">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="d6903-109">Para más información, vea [Datos de objeto binario grande &#40;Blob&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d6903-109">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="d6903-110">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d6903-110">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="d6903-111">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d6903-111">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="d6903-112">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="d6903-112">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="d6903-113">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="d6903-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="d6903-114">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d6903-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="d6903-115">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d6903-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6903-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="d6903-116">Options</span></span>  
 <span data-ttu-id="d6903-117">**Instrucción SQL**</span><span class="sxs-lookup"><span data-stu-id="d6903-117">**SQL statement**</span></span>  
 <span data-ttu-id="d6903-118">Muestra la instrucción SQL generada automáticamente y permite que se edite.</span><span class="sxs-lookup"><span data-stu-id="d6903-118">Displays the auto-generated SQL statement and lets it be edited.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6903-119">Si desea incluir un retorno de carro en la instrucción SQL, presione CTRL+ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d6903-119">If you want to include a carriage return in the SQL statement, press CTRL+ENTER.</span></span> <span data-ttu-id="d6903-120">Si presiona solamente ENTRAR, se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d6903-120">If you press only ENTER, the dialog box closes.</span></span>  
  
 <span data-ttu-id="d6903-121">**Autogenerar**</span><span class="sxs-lookup"><span data-stu-id="d6903-121">**Autogenerate**</span></span>  
 <span data-ttu-id="d6903-122">Restaura la instrucción SQL predeterminada (si se ha modificado) al hacer clic en **Autogenerar**.</span><span class="sxs-lookup"><span data-stu-id="d6903-122">Restore the default SQL statement, if you have modified it, by clicking **Autogenerate**.</span></span>  
  
  
