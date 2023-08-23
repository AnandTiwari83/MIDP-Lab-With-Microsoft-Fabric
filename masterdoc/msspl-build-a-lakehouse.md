### Hands-On-Lab: Build a lakehouse

#### Task 2.1: Activate SharePoint Online

1. To activate SharePoint Online, copy the **Office homepage link** and open this link inside the VM in a new tab:

   ```
   https://office.com
   ```

2. Click on **Sign in(1)**:

   ![01s](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/01s.png?raw=true)

3. If you see the prompt **Action Required**, click on **Ask Later(1)**:

   ![02s](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/02s.png?raw=true)

4. You have now successfully signed into **Office homepage** and activated **SharePoint Online*:

   ![03s](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/03s.png?raw=true)

>**Note:** This will be required for a particular task in the lab.

5. You can now close this tab and proceed to the next task.

----

#### Task 2.2: Create a lakehouse

1. From the newly created Power BI workspace, make use of the **Experience switcher(1)** located at the bottom left, and select **Data Engineering(2)**:

   ![exp-switcher-data-engg](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/01.png?raw=true)

2. In the **Data Engineering** tab, select **Lakehouse(1)** to create a lakehouse:

   ![select-lakehouse](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/02.png?raw=true)

3. In the **New lakehouse** dialog box, enter **wwilakehouse(1)** in the **Name** field, and click on **Create(2)** to create and open the new lakehouse:

   ![enter-wwilakehouse-name](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/03.png?raw=true)

----

#### Task 2.3: Ingest sample data

1. In the **Lakehouse explorer**, you see options to load data into lakehouse. Select **New Dataflow Gen2(1)**:

   ![select-dataflow-gen2](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/04.png?raw=true)

2. On the new dataflow pane, select **Import from a Text/CSV file(1)**:

   ![select-option-to-import-csv-file](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/05.png?raw=true)

3. On the **Connect to data source(1)** pane, select the **Upload file(2)** radio button, and then click on **Browse(3)**:

   ![Browse](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/06.png?raw=true)

4. In the Open window, navigate to the **C:\FabricFiles(1)** folder, select the **dimension_customer.csv(2)** file, and click on **Open(3)**:

   ![navigate-csv](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/07.png?raw=true)

5. After the file is uploaded, select **Next(1)**:

   ![selectnext](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/08.png?raw=true)

6. From the **Preview file data** page, preview the data and select **Create(1)** to proceed and return back to the dataflow canvas:

   ![select-create](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/09.png?raw=true)

7. It will open up a **Power Query** editor. In the **Query settings(1)** pane, verify whether **dimension_customer(2)** is reflecting under the **Name** field. 

   ![verify-name-and-lakehouse](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/10.png?raw=true)

8. Now, we will be removing the pre-configured **Data destination** and configuring it manually, click on the **X(1)** next to the Lakehouse icon under **Data destination**:

   ![click-x](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/11.png?raw=true)

9. It will open up a prompt which will ask you to  confirm to **Remove data destination**, click on **OK(1)**:

   ![click-ok](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/12.png?raw=true)
   
10. Now, in the **Power Query** editor, click on **Add data destination(1)**, and select **Lakehouse(2)**:

    ![set-data-lakehouse-dest](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/13.png?raw=true)

11. In the **Connect to data destination** pane, confirm the **Connection(1)**, and click on **Next(2)**:

    ![connection-next](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/14.png?raw=true)

12. In the **Choose destination target** pane, confirm the name of the table to be **dimension_customer(1)**. Now, expand your workspace and select **wwilakehouse(1)**, and click on **Next(3)**:

    ![data-destination-lakehouse](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/15.png?raw=true)

14. In the **Choose destination settings**, select **Replace(1)** as Update method. Select **Save Settings(2)** to return to the dataflow canvas:

    ![replace-as-update-method-save-settings](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/16.png?raw=true)

15. From the dataflow canvas, select **Publish(1)** at the bottom right of the screen:

    ![publish-canvas](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/17.png?raw=true)

16. A spinning circle next to the dataflow's name indicates publishing is in progress in the item view:

    ![dataflow-in-progress](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/18.png?raw=true)

17. Once publishing is complete, click on the **...(1)** and select **Properties(2)**:

    ![select-properties](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/19.png?raw=true)

18. Rename the dataflow to **Load Lakehouse Table(1)** and select **Save(2)**:

    ![rename-load-save](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/20.png?raw=true)

19. Select the **Refresh now(1)** option next to data flow name to refresh the dataflow. It runs the dataflow and moves data from the source file to lakehouse table:

    ![refresh-data-flow](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/21.png?raw=true)

20.  Once the dataflow is refreshed, select your lakehouse from the **Fabric workspace**:

     ![select-lakehouse](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/22.png?raw=true)

21. Now, you can view the **dimension_customer(1)** delta table. Select the table to preview its data:

    ![preview-customer-data](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/23.png?raw=true)

22. You can also use the SQL endpoint of the lakehouse to query the data with SQL statements. Select **SQL endpoint(1)** from the Lakehouse drop-down menu at the top right of the screen:

    ![sql-endpoint](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/24.png?raw=true)

23. Select **New SQL query(1)** to write your SQL statements:

    ![new-sql-query](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/25.png?raw=true)

24. Input the following SQL query which aggregates the row count based on the BuyingGroup column of the **dimension_customer** table:

    ```
    SELECT BuyingGroup, Count(*) AS Total
    FROM dimension_customer
    GROUP BY BuyingGroup
    ```

25. Click on **Run(1)** to run the query, and view the results:

    ![view-sql-query-results](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/26.png?raw=true)

----

#### Task 2.4: Build a report

1. From the workspace, select the **wwilakehouse default dataset(1)**. This dataset is automatically created and has the same name as the lakehouse:

   ![wwilakehouse-default-dataset](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/27.png?raw=true)

2. From the dataset pane, you can view all the tables. You have options to create reports either from scratch, paginated report, or let Power BI automatically create a report based on your data. For this lab, select **Auto-create(2)** under **Create a report(1)**:

   ![auto-create](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/28.png?raw=true)

3. Since the table is a dimension and there are no measures in it, Power BI creates a measure for the row count and aggregates it across different columns, and creates different charts as shown in the following image. You can save this report for the future by selecting **Save(1)** from the top ribbon:

   ![save-report](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/09/29.png?raw=true)

Congratulations! You have successfully learnt to create a lakehouse, ingest sample data and build a report.

