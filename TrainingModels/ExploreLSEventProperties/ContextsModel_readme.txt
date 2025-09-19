
How to use the "context exploration" model.

(i) Start SELES and open "Contexts.scn".
(ii) Open the probe (Dynamic Models/Simulation Probe). Select an appropriate
     property (e.g. Transitions) and slowdown (e.g. 1000 milliseconds = 1s)
(iii) Open the simulation control and press "Simulate".  For more details
   select a Step Size of 1 "DeciStep" and press "Step" repeatedly to step
   through the simulation.


Display dialogs (from "DISPLAY" expressions) will be displayed on the
screeen, one for each preliminary/consequent context in each property.
Each will show the context type, time and some additional info available
within the context (e.g. event id, cluster id).  Pressing "OK" will close
the dialog, but it may be re-displayed by a future "DISPLAY" expression.
Pressing "Cancel" will stop this particular display dialog from being redisplayed
until the models are reloaded.  Thus, once you see the pattern for some of
the properties, start pressing "Cancel" to focus on the remaining properties.
Be sure to follow the cell, cluster and event id's to see what is going on.
If you want to allow display of a dialog for which you pressed "Cancel", stop
the simulation and press the "reload button" (second to last button on the toolbar).

The model tracks the number of active cells, clusters and event instances
and assigns each active cell and cluster a unique id (event instances are
automatically assigned unique id's by SELES). Thus, the model needs to
identify when active cells, clusters or event instances are created or
terminated.

The various variable values can be seen on the probe, simulation dialog and
displayed dialogs.

There are five output rasters designed to show the event location, the cells 
selected for inition in a time step, the cells in which the event occurs, the
potential recipient cells and the actual recipient cells. Each shows values from
0 (black) to 10 which indicate the id of the event instance that visited them.
The model by default only shows results from at most 10 event instances (if you
want more, change the constant "MaxInstances" in Model.sel.

The first instance gets scheduled to be processed at step 1, and the subsequent ones
at intervals of 10 steps.  


Try to follow the logic of this model as described to see the order in which SELES
processes properties, how active cells, clusters and event instances are managed,
and which variables are avaiable where (i.e. what the contexts are).

Then try modifying the model (e.g. comment out the NUMCLUSTERS property to force
PROBINIT to be an absolute probability).  Reload the model and follow the new logic.



