# ASPxTreeList - How to drag and drop multiple nodes
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/t501420/)**
<!-- run online end -->


The sample illustrates how to drag and drop multiple nodes in ASPxTreeList when selection is enabled. To replace selected nodes from one parent node to another, it's sufficient to change the selected nodes' parent property at the DataSource level. This can be done by using the [ASPxTreeList.GetSelectedNodes](https://documentation.devexpress.com/AspNet/DevExpress.Web.ASPxTreeList.ASPxTreeList.GetSelectedNodes.method(DZAdlg)) method and the EventArgs [e.Node](https://documentation.devexpress.com/AspNet/DevExpress.Web.ASPxTreeList.TreeListNodeEventArgs.Node.property) and [e.NewParentNode](https://documentation.devexpress.com/AspNet/DevExpress.Web.ASPxTreeList.TreeListNodeDragEventArgs.NewParentNode.property) properties in the server-side [ProcessDragNode](https://documentation.devexpress.com/AspNet/DevExpress.Web.ASPxTreeList.ASPxTreeList.ProcessDragNode.event) event handler. The **DataHelper** class is used to generate data and move node(s) at the data source level.

All selected nodes are shown in a transparent popup on dragging. This can be achieved by handling the [StartDragNode](https://documentation.devexpress.com/AspNet/DevExpress.Web.ASPxTreeList.Scripts.ASPxClientTreeList.StartDragNode.event) event. After the StartDragNode event is raised, a div container is created after the form element. You can find this container, clone a table row inside the div container, and assign selected node values to cloned rows. The div container is created after the StartDragNode event is handled, so it's necessary to implement your own custom function and call it asynchronously from the StartDragNode event handler.

***See also*** <br />
[TreeList - How to drag and drop multiple selected nodes](https://github.com/DevExpress-Examples/TreeList-How-to-drag-and-drop-multiple-selected-nodes)
