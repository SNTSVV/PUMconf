# PUMConf

## Overview 

{% include youtube.html id=uLIio468jWE %}

PUMConf (Product line Use case Model Configurator) is a tool integrated with an industrial requirements management tool (i.e., IBM Doors) as a plug-in relying on Natural Language Processing (NLP) to report inconsistencies in Product Line (PL) use cases and contradicting decisions, and to automatically generate Product Specific (PS) use case and domain models.
The key features of PUMConf are:

1. Managing PL use cases and domain model: this feature allows the analyst to create, update, and delete PL use case diagram, specifications, and domain model by using the selected modeling tools (i.e., IBM Doors, Papyrus, and Rhapsody) adopted in PUMConf.
2. Checking consistency of PL use cases and domain model: our tool automatically checks (1) if the PL use case specifications conform to the RUCM template and its product line extensions, (2) if the PL use case diagram is consistent with the PL use case specifications, and (3) if the PL domain model is consistent with the PL use case specifications.
3. Getting configuration decisions from the analyst and checking consistency of these decisions: the analyst makes a decision for each variation point in the list, while the tool checks automatically the consistency of the decision with prior decisions.
4. Generating PS use cases and domain model:  After the decisions are made, the PS use cases and domain model are generated from the PL models based on some transformation rules.
5. Identifying the change impact for evolving configuration decisions in PL use case diagrams: Changes on configuration decisions for the PL use case diagram have an impact on prior decisions as well as on subsequent decisions to be made. Therefore, our impact analysis approach checks (i) if the change causes any contradiction with prior decisions, (ii) if there is any prior decision which becomes invalid, (iii) if any additional variation point should be considered for decision-making, and (iv) if any subsequent decision should be constrained to ensure the consistency of decisions.
6. Incrementally reconfiguring PS use case models: The PS use case diagram and specifications are incrementally reconfigured by focusing only on the changed configuration decisions and their side effects. We implemented a model differencing pipeline which identifies decision changes to be used in the regeneration of PS models. There are two sets of decisions: (i) the set of previously made decisions used to initially generate the PS use case models and (ii) the set of decisions including decisions changed after the initial generation of the PS models. PUMConf compares the two sets to incrementally regenerate the PS use case models.
7. (New Feature) Test Case Classification for Use Case-Driven Testing in Product Lines: System test cases for a new product are derived by reusing system test cases from previous product(s), and by identifying use case scenarios of the new product that have not been tested so far in the product family. To reuse the existing system test cases, PUMConf identifies changes in the decisions made to configure a new product (e.g., selecting a variant use case), compares the decisions and classify them as new, deleted and updated, then identifies the impacted parts of the use case models of the previous product(s). By using the trace links from the impacted parts of the use case models to the system test cases, PUMConf automatically classifies the existing system test cases to be reused as obsolete, retestable, and reusable. An obsolete test case exercises an invalid execution sequence of use case steps in the new product. A retestable test case exercises an execution sequence of use case steps that has remained valid in the new product, except for internal steps representing internal system operations (e.g., reset of counters) whereas a reusable test case exercises an execution sequence of use case steps that has remained valid in the new product. In addition, PUMConf automatically identifies the use case scenarios of the new product that have not been tested before, and provides information on how to modify existing system test cases to cover these new, untested use case scenarios.
8. (New Feature) Test Case Prioritization for Use Case-Driven Testing in Product Lines: System test cases are automatically prioritized based on multiple risk factors such as fault proneness of requirements and requirements volatility in the product line. To this end, PUMConf relies on prediction models; more precisely, it leverages logistic regression models that capture how likely changes in these risk factors impact the failure likelihood of each test case. First, PUMConf automatically identifies significant factors for prioritizing the test cases of a new product. It relies on the p-value computed by the Wald test on the logistic regression model trained by including all the considered factors. Second, PUMConf prioritizes test cases by relying on the probability calculated by the regression model. The test cases are sorted in descending order of probability and presented to engineers.

PUMConf has been successfully evaluated on an industrial case study.


## Download and installation

To install and run PUMConf please: 

1. Download the installation package and example models together: PUMConf_Distribution
2. Follow PUMConf user manual: [PUMConf_UserManual](data/PUMConf_UserManual.pdf}



