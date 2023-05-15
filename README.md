# Predictive Maintenance
 Predictive maintenance model building based on a exemple dataset from sensors applied in machines, it is expected to find a model that predicts whether the machine may have a problem in the next 24 hours and which component must be changed to avoid failure and its stoppage. This example contains 5 data sets used for prediction:
 
 - Telemetry Time Series Data (PdM_telemetry.csv): It consists of hourly average of voltage, rotation, pressure, vibration collected from 100 machines for the year 2015.
- Error (PdM_errors.csv): These are errors encountered by the machines while in operating condition. Since, these errors don't shut down the machines, these are not considered as failures.
- Maintenance (PdM_maint.csv): If a component of a machine is replaced, that is captured as a record in this table. Components are replaced under two situations: 1. During the regular scheduled visit, the technician replaced it (Proactive Maintenance) 2. A component breaks down and then the technician does an unscheduled maintenance to replace the component (Reactive Maintenance). This is considered as a failure and corresponding data is captured under Failures.
- Failures (PdM_failures.csv): Each record represents replacement of a component due to failure. This data is a subset of Maintenance data.
- Metadata of Machines (PdM_Machines.csv): Model type & age of the Machines.

The data is collected at an hourly rate.

The analysis will consist of two parts, a Exploratory Data Analysis (EDA), to gain insights, mainly regarding the relationship between variables, analyzing both the average across all machines and of individual machines. In addition to obtaining some important parameters when it comes to preventive maintenance (scheduled achievements calculated from a forecast of when the machine or component may fail). From this analysis, a function was built that unites the insights in a way that best fits the dataset for building the model. The entire conclusion that led to this choice is described in the notebook.

Afterwards, different models (also explained in the notebook) were applied to the training data, and based on the recall value, the model that would be used in this set of machines was selected.
 
Recall was the main model validation metric because it focuses on minimizing false negatives, which means correctly identifying all positive cases (when failure occurs, because changing a component before the right time is still less expensive than corrective maintenance that result in costly consequences such as unplanned downtime, maintenance delays, or safety hazards).

The final result is a model that predicts whether the machine will fail in 24 hours and which component will fail. The results, chosen model, and conclusions can be seen in the notebook.


