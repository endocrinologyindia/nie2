---
{"dg-publish":true,"permalink":"/notes-in-endocrinology/technocrinology/insulin-algorithm/"}
---


<script data-goatcounter="https://endocrinologyindia.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>
# Insulin Algorithm
Author: [[About Us/Dr. Om J Lakhani\|Dr. Om J Lakhani]]

> If you find this useful, please use the link to see the various ways in which you can [[Support us/Support us →\|Support us →]]

**Components of an Automated Insulin Delivery System**

- Q. What are the components required in an algorithm to make an Automated Insulin Delivery system?
    - 1. A system that measures glucose - real-time Continuous Glucose Monitoring (rtCGM)
    - 2. A system that delivers insulin
    - 3. An algorithm that connects the two
    - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FMedical_learning%2F5vI_ElYZRI.jpeg?alt=media&token=9e0c8e47-32d2-433a-9282-5d100ec8eab0)

- Q. What are the questions and delays for the Automated Insulin Delivery system while making such algorithms?
    - 1. The delay in the glucose measurement in the interstitial fluid (ISF) versus blood glucose
    - 2. The absence of hepatic extraction
    - 3. The lack of a second hormone (glucagon)
    - 4. Delay in absorption from the subcutaneous to the systemic circulation

**Various Insulin Algorithms**

- Q. Which are various insulin algorithms developed by various research groups?
    - Proportional Integrative Differential (PID) algorithm: This algorithm uses current glucose values as initial conditions and considers insulin sensitivity, insulin action, carbohydrate intake, physical activity, and stress.
    - Model Predictive Controller (MPC) algorithm: This algorithm, along with its modifications, calculates the insulin infusion rate as a function of time and changing glucose concentration.
    - Hypoglycemic Predictive Algorithms (HPA): These algorithms focus on predicting hypoglycemic events.
    - Fuzzy Logic algorithm used by DreaMed (also called MD logic): This algorithm utilizes a fuzzy logic approach for insulin delivery.
    - Neural Networks: These are used for calculating insulin infusion rates, taking into account various parameters like insulin sensitivity and carbohydrate intake.

**PID Algorithm**

- Q. Which model is used by the Medtronic 780G pump?
    - The PID algorithm.

- Q. Help us understand the PID system in simple words.
    - The PID system works by continuously adjusting insulin delivery in response to real-time changes in blood glucose levels, taking into account both the immediate and historical glucose data, as well as predicting future trends for optimal insulin regulation.
    - Responds to Now (Proportional): It quickly adjusts insulin based on current blood sugar levels. High sugar? It gives more insulin. Low sugar? It reduces insulin.
    - Remembers the Past (Integral): It keeps track of past blood sugar levels and makes adjustments to prevent long-term highs or lows.
    - Predicts the Future (Derivative): It looks at how fast blood sugar is changing and adjusts insulin to prevent future highs or lows before they happen.
    - Customized for You: It changes its behavior based on your body's needs, like how much insulin you usually need and how food or exercise affects you.
    - Learns Over Time: Some advanced systems can learn from your patterns and get better at managing your blood sugar over time.

- Q. What is the concept of a microbolus?
    - The concept of a microbolus in adaptive basal insulin delivery can be understood as follows:
        - Time Division for Calculation: The time axis is divided into equal segments, and the glucose concentration is calculated for each segment based on the insulin dose.
        - Microbolus Delivery: A microbolus is a small dose of insulin. It's decided if a microbolus should be delivered by calculating future glucose values for each time segment. These calculations are based on the current glucose levels and the amount of insulin already in the body (known as "insulin on board").
        - Frequency and Duration Considerations: The number of time segments and therefore the frequency of potential microbolus delivery depends on how often glucose values are measured and the duration of insulin action. For example, if a real-time Continuous Glucose Monitoring (rtCGM) system provides a glucose value every 5 minutes and insulin acts for 4 hours, this results in 48 time segments.
        - Adaptive Delivery: If the calculated future glucose values fall within the desired range, a microbolus is delivered. If not, the insulin dose is adjusted accordingly, either increased or decreased based on the glucose prediction.
    - In simple terms, a microbolus is a small, calculated dose of insulin delivered at frequent intervals, adjusted based on real-time and predicted glucose levels to maintain optimal blood sugar control.

- Q. What microbolus parameters does the Medtronic system use?
    - It uses the rule of 1800 to calculate the insulin sensitivity factor (ISF) over an average insulin dosing over the last 6 days.
    - It sets a target glucose of 120 mg/dL.

- Q. If in the auto-mode the microbolus is correcting for the glucose, then why do we need the meal-time bolus additionally?
    - This is because the company, based on FDA regulations, has placed a limit of a maximum of 2.5 times the basal rate increase compared to the baseline levels.

- Q. What is basal-safe?
    - The concept of "Basal-Safe" in automated insulin delivery systems, particularly in the context of the 670G system, can be understood as follows:
        - Safety Feature: Basal-Safe acts as a safety mechanism to prevent the system from switching back to manual mode in uncertain metabolic situations or when glucose data are missing.
        - Minimum Basal Insulin Delivery: In Basal-Safe mode, the insulin pump operates at a minimum basal insulin delivery rate. This rate is determined based on the insulin dosage set in the automatic (Auto) mode of the pump.
        - Response to User Inaction: If the person with diabetes (PwD) does not respond to an alarm within a specified time (e.g., 90 minutes), the system will switch from its automatic mode to manual mode.
        - Limited PID Algorithm Functionality: In this mode, the PID (Proportional-Integral-Derivative) algorithm used in the 670G system continues to function based on current glucose data. However, it does not simulate future glucose levels or incorporate advanced predictive features.
    - In essence, Basal-Safe is a mode that ensures continuous, minimal insulin delivery under certain conditions, prioritizing safety and preventing abrupt changes to manual insulin delivery.
    - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FMedical_learning%2FQsA2Sj9ayJ.jpeg?alt=media&token=a3c64f21-ddaa-41fa-bf97-daffdbd791fb)

**MPC Algorithm**

- Q. Summarize the key concepts of the MPC algorithm?
    - Predictive Nature: MPC forecasts future glucose levels based on current data. It uses mathematical models to predict how glucose levels will change in response to insulin delivery and other variables.
    - Control Strategy: The algorithm adjusts insulin delivery in anticipation of future glucose changes, not just in response to current levels. This proactive approach helps to prevent high and low blood sugar levels.
    - Incorporation of Multiple Variables: MPC takes into account various factors that affect blood sugar, such as carbohydrate intake, physical activity, insulin sensitivity, and insulin action time.
    - Continuous Adjustment: The algorithm continuously recalculates predictions and adjusts insulin delivery accordingly. This dynamic adjustment allows for more precise and personalized insulin management.
    - Feedback Loop: MPC operates in a closed-loop system, where continuous glucose monitoring data are used to update the predictive model and adjust insulin dosing in real-time.
    - Safety and Constraints: MPC algorithms often include safety constraints to prevent over- or under-dosing of insulin, ensuring the patient's safety.
    - Learning and Adapting: Some MPC systems can adapt to changes in the patient's insulin sensitivity or routine, improving their predictive accuracy over time.
    - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FMedical_learning%2FckemuvEltS.jpeg?alt=media&token=4db5ee4b-2d20-4c71-baa2-c7267690e760)

- Q. What are the differences between the MPC and the PID algorithm?
    - Predictive vs. Reactive Approach:
        - MPC: Primarily predictive, it forecasts future glucose levels and adjusts insulin delivery accordingly.
        - PID: Reactive, adjusting insulin based on current and past glucose levels, with some predictive capacity in the derivative component.
    - Complexity of the Model:
        - MPC: More complex, using sophisticated models to predict future blood glucose levels.
        - PID: Simpler in design, based on proportional, integral, and derivative components without detailed future predictions.
    - Data Utilization:
        - MPC: Incorporates a broader range of data, including predictions about future states.
        - PID: Focuses on current and past data, adjusting insulin delivery based on these factors.
    - Customization and Adaptation:
        - MPC: Can be more adaptive, learning from ongoing data to improve predictions and control.
        - PID: Has limited learning capabilities, primarily adjusting based on predefined rules.
    - Safety and Constraints:
        - MPC: Often includes various safety constraints and can adjust for anticipated risks.
        - PID: Relies on immediate data, with less emphasis on anticipating future events.
    - Implementation Complexity:
        - MPC: Generally requires more computational power and sophisticated algorithms.
        - PID: Easier to implement and requires less computational resources.

- Q. Which pump works on the MPC algorithm?
    - The t:slim pump.

**Fuzzy Logic Algorithm**

- Q. What is MDLAP?
    - MDLAP stands for Medical Doctor Logic Artificial Pancreas.
    - It is a form of algorithm based on fuzzy logic.

- Q. What is Fuzzy logic?
    - Fuzzy logic is a way of processing information that is more similar to human reasoning than traditional binary logic. In simple terms, it allows for more flexible and nuanced decision-making. Here's a breakdown to understand it better:
        - Grades of Truth: Unlike traditional logic where things are black and white (true or false), fuzzy logic deals with degrees of truth. For example, instead of saying "it is raining" or "it is not raining", fuzzy logic allows for statements like "it is somewhat raining" or "it is heavily raining".
        - Real-world Situations: Fuzzy logic is useful in dealing with situations that are not clear-cut or are ambiguous. In real life, many things are not just yes or no, but somewhere in between. Fuzzy logic helps in making decisions in such scenarios.
        - Rules and Degrees: In fuzzy logic, you create rules that use degrees of truth rather than absolute true or false statements. For instance, a rule might say, "If the weather is slightly cold, then turn the heater on a little bit."
        - Applications: It's used in various applications where decision-making requires a range of possibilities, like climate control systems, washing machines, or even more complex systems like the automated insulin delivery systems.
    - In essence, fuzzy logic is about handling the concept of partial truth, where something can be partially true and partially false at the same time, which is more reflective of how humans think and reason in everyday life.

- Q. So why are MDLAP and Fuzzy logic different from the earlier algorithms?
    - Previous AID Algorithms: Prior algorithms like PID and MPC addressed individual patient needs roughly, without fully considering the complexity and non-linearity of biological systems. This limited their ability to subtly regulate blood sugar levels using just one input (glucose level) and one output (insulin delivery).
    - Limitations in Current AID Systems: Existing hybrid AID systems (like 670G, MiniMed 780G, and t:slim X2 CONTROL IQ) mostly manage basal insulin delivery and, when necessary, correction boluses. They do this through a linear control algorithm, which regulates relatively small insulin doses (referred to as microboli).
    - Introduction of Fuzzy Logic: Fuzzy logic in AID systems is more nuanced. It considers various factors such as:
        - The remaining effective insulin in the bloodstream from previous doses.
        - Current glucose levels and how they might change with further insulin delivery.
        - External influences, like physical activity.
    - Fuzzy Logic Rules: These are based on the treatment rules used by patients and their doctors. Examples include:
        - Simple rules like "if glucose level is too high, deliver insulin."
        - More complex rules like "if glucose level is high and the patient is exercising, do not deliver insulin."
    - Personalization: MDLAP (a type of fuzzy logic system) employs rules grounded in diabetological knowledge, tailored to each patient. This personalization takes into account individual diabetes management aspects such as insulin delivery regimens, correction factors, insulin pharmacodynamics, and typical activities.

- Q. What is the opposite of Fuzzy logic?
    - Binary logic.
    - Binary logic is 0 and 1 - either it is cold or hot.
    - Fuzzy logic - is cold, hot, warm, I feel cold, I feel warm, a little warm, a tad bit warm, etc.

Reference:

1. Thomas A, Heinemann L. Algorithms for automated insulin delivery: an overview. Journal of Diabetes Science and Technology. 2022 Sep;16(5):1228-38.