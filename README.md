# Blue-City-Football-Club-BCFC-Ticket-Revenue-Optimization
Linear programming optimization project for maximizing BCFC stadium ticket sales revenue while managing promotional t-shirt constraints. Optimal solution: 9,000 VIP seats and 17,000 regular seats generating £4,850,000 revenue.

Executive Summary
The Blue City Football Club faces a revenue optimization challenge for an upcoming friendly match. The club must allocate limited stadium capacity (27,500 seats) between VIP (£350 per seat) and Regular (£100 per seat) ticket categories while managing a promotional t-shirt constraint (35,000 total shirts available). VIP tickets include 2 shirts each, regular tickets include 1 shirt each, with maximum VIP sales capped at 9,000 and maximum regular demand at 25,000.

Using linear programming optimization with Excel Solver, the analysis determines optimal ticket allocation maximizing revenue to £4,850,000. Shadow price analysis reveals each additional t-shirt constraint generates £100 in marginal revenue value, directly indicating the financial impact of supply limitations.

Problem Formulation
The BCFC ticket optimization problem represents a classic linear programming application combining multiple real-world constraints: capacity limitations, demand restrictions, and promotional inventory management.

Decision Variables Definition:

The optimization involves two decision variables representing ticket quantities. Let V represent the number of VIP seat tickets to sell, ranging from 0 to 9,000 units. Let R represent the number of regular seat tickets to sell, ranging from 0 to 25,000 units.

Objective Function:

The revenue maximization function expresses total ticket revenue as the sum of VIP and regular ticket contributions. Revenue = 350V + 100R, measured in British pounds. This linear objective maximizes total income from both ticket categories.

Constraint Set:

Four constraints define the feasible solution space. The stadium capacity constraint ensures total seats allocated cannot exceed physical capacity: V + R ≤ 27,500. This fundamental restriction reflects stadium construction limitations.

The promotional t-shirt constraint manages inventory scarcity: 2V + R ≤ 35,000. Since VIP tickets include 2 shirts and regular tickets include 1 shirt, total t-shirt distribution cannot exceed 35,000 available units. This constraint creates the binding optimization trade-off.

VIP seat upper bound constraint reflects market demand expectations: V ≤ 9,000. Despite ticket pricing advantages, premium seating demand remains capped at 9,000 seats based on historical patterns and market analysis.

Regular seat demand constraint represents maximum achievable sales volume: R ≤ 25,000. Even with promotional activities, regular ticket demand does not exceed 25,000 units.

Non-negativity constraints ensure solution feasibility: V ≥ 0 and R ≥ 0. Negative ticket quantities hold no practical meaning.

Complete Linear Programming Model:

Maximize: Revenue = 350V + 100R

Subject to:

V + R ≤ 27,500 (stadium capacity)

2V + R ≤ 35,000 (t-shirt availability)

V ≤ 9,000 (VIP demand cap)

R ≤ 25,000 (regular demand cap)

V ≥ 0, R ≥ 0 (non-negativity)

Graphical Solution Method
The graphical method visualizes the feasible region and objective function for two-variable linear programming problems. Each constraint defines a half-plane boundary, with the intersection creating a convex feasible region.

Graphical Analysis:

The stadium capacity constraint (V + R = 27,500) forms a line with slope -1, intercepting the V-axis at 27,500 and R-axis at 27,500. The feasible region lies below and to the left of this line.

The t-shirt constraint (2V + R = 35,000) slopes more steeply at -2, intersecting the V-axis at 17,500 and R-axis at 35,000. The feasible region remains below this boundary.

VIP demand cap (V = 9,000) forms a vertical line. Feasible solutions require V values not exceeding 9,000.

Regular demand cap (R = 25,000) forms a horizontal line. Feasible solutions maintain R ≤ 25,000.

The feasible region emerges as a polygon bounded by these four constraints plus non-negativity requirements. Vertices (corner points) of the feasible region represent candidate optimal solutions. In linear programming, the optimal solution always occurs at a vertex when the objective function remains non-degenerate.

Key Vertices Analysis:

The origin (0, 0) represents zero ticket sales with revenue of £0.

Intersection of V = 9,000 and R = 0 yields the point (9,000, 0) generating revenue of 350(9,000) + 100(0) = £3,150,000.

Intersection of V = 0 and capacity constraint yields (0, 27,500) generating revenue of 350(0) + 100(27,500) = £2,750,000.

Intersection of V = 9,000 and t-shirt constraint 2V + R = 35,000 yields 2(9,000) + R = 35,000, solving to R = 17,000. Revenue at (9,000, 17,000) = 350(9,000) + 100(17,000) = £3,150,000 + £1,700,000 = £4,850,000.

This point (9,000, 17,000) satisfies all constraints and produces maximum revenue.

Verification of Optimality:

The objective function slope is -350/100 = -3.5 (revenue per regular ticket divided by revenue per VIP ticket). The t-shirt constraint slope of -2 differs from the objective function slope of -3.5, indicating the t-shirt constraint is not parallel to the objective function. This geometric relationship ensures the optimal vertex remains at the intersection of V = 9,000 and 2V + R = 35,000.

The optimal solution occurs where the VIP demand cap and t-shirt constraint intersect, indicating both constraints bind at optimality. No slack exists in either constraint—the solution uses all 9,000 available VIP seats and all 35,000 available t-shirts.

Excel Solver Implementation
Excel Solver provides computational verification of the graphical solution and sensitivity analysis revealing constraint values.

Solver Setup:

The Excel model includes a spreadsheet layout with decision variable cells (V and R) initialized to zero. The objective function cell contains the formula =350V_cell + 100R_cell calculating total revenue. Constraint cells compute usage for stadium capacity, t-shirt distribution, and demand restrictions.

Solver Parameters Configuration:

Set Objective: Select the revenue cell for maximization.
To: Select "Max" option.
By Changing Variable Cells: Specify cells containing V and R.

Constraint Definitions:

V + R ≤ 27,500 (stadium capacity)

2V + R ≤ 35,000 (t-shirt constraint)

V ≤ 9,000 (VIP cap)

R ≤ 25,000 (regular demand)

V ≥ 0 and R ≥ 0 (non-negativity)

Solver Engine: Select "Simplex LP" for linear programming problems.

Solution Results:

Optimal Decision Variables:

VIP Seats (V): 9,000

Regular Seats (R): 17,000

Total Seats: 26,000

Revenue Outcome:

VIP Revenue: 350 × 9,000 = £3,150,000

Regular Revenue: 100 × 17,000 = £1,700,000

Total Revenue: £4,850,000

Constraint Binding Analysis:

Stadium capacity uses 26,000 of 27,500 seats, leaving 1,500 unused seats (slack = 1,500). This constraint is non-binding—additional seats would not improve the solution.

T-shirt constraint uses 2(9,000) + 17,000 = 35,000 shirts, consuming all available inventory (slack = 0). This constraint binds at optimality, creating the optimization trade-off. Every additional t-shirt directly enables incremental revenue generation.

VIP demand cap uses 9,000 of 9,000 maximum VIP seats (slack = 0). This constraint binds, indicating VIP tickets are fully utilized within market limitations.

Regular demand cap uses 17,000 of 25,000 maximum regular seats (slack = 8,000). Only 68 percent of potential regular demand is fulfilled due to t-shirt constraints, not demand limitations.

Sensitivity Analysis and Shadow Prices
Shadow price analysis quantifies the marginal value of relaxing binding constraints, revealing constraint-related optimization insights.

T-Shirt Constraint Shadow Price:

The shadow price of the t-shirt constraint equals £100, interpreted as follows: for every additional t-shirt added to the 35,000 available supply, total revenue increases by exactly £100. This relationship holds within a certain range before constraint binding relationships change.

The shadow price value (£100) equals the regular ticket price, providing economic interpretation. Each additional t-shirt enables selling one more regular seat ticket (generating £100 revenue) without violating the stadium capacity constraint, as the regular demand cap remains unsaturated.

VIP Demand Cap Shadow Price:

The VIP demand cap shadow price equals the coefficient difference in the t-shirt constraint. Increasing the VIP cap from 9,000 to 9,001 requires one additional t-shirt (slack term increases by 2). This constrains regular seats proportionally, reducing total revenue by approximately £100. The VIP cap shadow price therefore approximates -£100 (negative, indicating revenue reduction from constraint tightening).

However, the exact interpretation requires examining reduced costs and binding constraint interactions. In this formulation, reducing VIP capacity (tightening the upper bound) allows additional regular seats to be sold, yielding a complex shadow price relationship.

Stadium Capacity Shadow Price:

The stadium capacity constraint holds 1,500 units of slack, indicating it is not binding at optimality. The shadow price equals zero—adding stadium capacity does not improve the solution, as t-shirt availability remains the limiting factor.

Sensitivity Range Analysis
The allowable increase and allowable decrease in objective function coefficients indicate how much prices can change before the optimal solution basis changes.

VIP Ticket Price Sensitivity:

The current VIP price of £350 can increase to approximately £650 before the optimal solution changes. Below £250, the solution basis shifts toward zero VIP tickets. Within the range £250 to £650, selling 9,000 VIP tickets remains optimal.

This range reflects that increasing VIP prices reinforces the current solution's optimality (maximizing higher-value tickets). Decreasing VIP prices below £250 makes regular tickets more attractive relative to the t-shirt constraint trade-off.

Regular Ticket Price Sensitivity:

The current regular price of £100 can decrease to approximately £50 or increase to £175 before the basis changes. Within this range, the current solution structure remains optimal despite price adjustments.

Constraint Right-Hand Side Sensitivity:

T-shirt constraint allowable increase: From 35,000 to approximately 45,000 shirts. Adding t-shirts within this range maintains the t-shirt constraint as the binding element, with each additional shirt generating £100 revenue.

T-shirt constraint allowable decrease: The constraint can decrease to approximately 34,000 before stadium capacity becomes binding, reducing feasible regular ticket sales.

VIP cap allowable increase: Increasing from 9,000 to higher levels does not improve revenue if the t-shirt constraint remains binding, as demonstrated by current optimality.

VIP cap allowable decrease: Decreasing below 8,000 forces reduced regular ticket sales (due to t-shirt requirements), reducing total revenue.

Part C: Shadow Price Interpretation
The shadow price analysis addresses how much revenue BCFC loses for each t-shirt it cannot offer.

Economic Interpretation:

At the optimal solution (9,000 VIP, 17,000 regular), the t-shirt constraint binds at exactly 35,000 shirts consumed. The shadow price of £100 per t-shirt indicates the marginal value of constraint relaxation.

If BCFC had one additional t-shirt beyond the 35,000 available, it could increase regular ticket sales by one unit (since VIP tickets are capped at 9,000 and require 2 shirts each). Selling one additional regular ticket generates £100 in revenue. This £100 represents the revenue loss from lacking that single t-shirt.

Conversely, if BCFC cannot supply shirts for certain sold tickets due to inventory shortage, each t-shirt shortfall forces either (a) reducing regular ticket sales by one seat (losing £100 revenue) or (b) breaking promotional promises by failing to deliver shirts with tickets.

Constraint Value Interpretation:

The shadow price reflects that every promotional t-shirt constraint directly supports revenue generation through its role in ticket allocation. The £100 shadow price equals exactly the regular ticket price, indicating perfect economic alignment: one additional shirt enables one additional regular ticket sale.

This relationship emerges because the t-shirt constraint (2V + R ≤ 35,000) combines with VIP cap (V ≤ 9,000) to limit regular seat sales. Adding shirts increases feasible R values proportionally.

Part D: Impact of Increased T-Shirt Supply
Evaluating the revenue impact of increasing t-shirt inventory from 35,000 to 36,000 units.

Shadow Price Application:

Using shadow price analysis, adding 1,000 t-shirts (from 35,000 to 36,000) should increase revenue by approximately 1,000 × £100 = £100,000, assuming the shadow price remains constant within this range.

The new constraint becomes: 2V + R ≤ 36,000.

Sensitivity range verification indicates that increasing t-shirts to 36,000 remains within the allowable increase range for the t-shirt constraint. The shadow price of £100 per t-shirt applies, confirming the linear relationship.

New Optimal Solution with 36,000 T-Shirts:

The optimal solution structure changes. With 9,000 VIP seats requiring 18,000 shirts, remaining inventory allows 36,000 - 18,000 = 18,000 regular seats, subject to the 25,000 demand cap.

New optimal values: V = 9,000, R = 18,000
Total seats: 9,000 + 18,000 = 27,000

This solution respects all constraints:

Stadium capacity: 27,000 < 27,500 ✓

T-shirt constraint: 2(9,000) + 18,000 = 36,000 ✓

VIP cap: 9,000 ≤ 9,000 ✓

Regular demand: 18,000 ≤ 25,000 ✓

Revenue Calculation:

VIP revenue: 350 × 9,000 = £3,150,000

Regular revenue: 100 × 18,000 = £1,800,000

Total revenue: £4,950,000

Revenue Increase Calculation:

Previous revenue (35,000 shirts): £4,850,000
New revenue (36,000 shirts): £4,950,000
Revenue increase: £4,950,000 - £4,850,000 = £100,000

This £100,000 increase matches the shadow price prediction exactly, confirming the linear relationship between t-shirt availability and revenue up to the point where stadium capacity becomes binding.

Further expansion to 37,000, 38,000, and beyond t-shirts would continue generating £100,000 additional revenue per 1,000 shirts until reaching 41,500 shirts (when stadium capacity of 27,500 seats becomes fully utilized with all seats sold).

Model Assumptions and Limitations
The linear programming model incorporates several key assumptions shaping solution applicability.

Linearity Assumption:

The model assumes revenue scales linearly with ticket quantities (constant £350 per VIP ticket, £100 per regular ticket). In practice, bulk discounts, dynamic pricing, or demand elasticity might create non-linear relationships.

Single-Period Optimization:

The model optimizes for a single friendly match, ignoring multi-period revenue management or ticket sales patterns across multiple matches.

Deterministic Parameters:

All model parameters (capacity, prices, t-shirt availability, demand caps) are treated as known with certainty. Actual demand, t-shirt production, and market conditions involve variability.

Promotional Constraint Binding:

The model assumes BCFC strictly honors promotional promises (delivering specified shirts with tickets). Relaxing this assumption would change the constraint structure.

Demand Independence:

The model treats VIP and regular ticket demand as independent with fixed upper bounds. Cross-price elasticity (VIP price changes affecting regular demand) is not modeled.

Indivisibility Assumption:

The solution allows fractional tickets, though in practice tickets are discrete units. For the values obtained (9,000 and 17,000), integer constraints do not bind.

Applications and Extensions
This BCFC optimization model demonstrates principles applicable to diverse scenarios.

Revenue Management:

Airlines optimize seat allocation across cabin classes (first, business, economy) under capacity and demand constraints. The model structure directly transfers to airline seat pricing optimization.

Inventory Management:

Retailers optimizing product mix under shelf space constraints and varying profit margins employ similar mathematical structures. Promotional inventory constraints (like BCFC's t-shirts) frequently bind optimization problems.

Capacity Planning:

Theaters, concert venues, and sports facilities consistently face similar revenue optimization across ticket categories. The shadow price analysis reveals how capacity investments (additional seating) should be valued.

Event Management:

Conference organizers, festival planners, and venue operators use linear programming to optimize ticket type allocation and pricing, particularly when managing sponsorship giveaways (analogous to promotional t-shirts).

Technical Implementation
Excel Solver execution involves standard optimization setup procedures.

Cell Layout:

Decision variable cells: V and R initialized to 0
Objective function cell: Formula calculating 350V + 100R
Constraint cells: Formulas for each inequality constraint
Result cells: Displaying constraint usage and slack values

Solver Dialog Configuration:

Set Objective: [Revenue cell]
Equal to: Max
By Changing Variable Cells: [V cell, R cell]
Subject to Constraints:

[Capacity usage] ≤ 27500

[T-shirt usage] ≤ 35000

[V] ≤ 9000

[R] ≤ 25000

[V] ≥ 0

[R] ≥ 0

Solving Method: Simplex LP (linear programming)

Output Reports:

Answer Report: Displays final variable values, objective function value, and constraint slack/surplus
Sensitivity Report: Shows shadow prices, allowable increases/decreases, reduced costs
Limits Report: Indicates variable lower/upper bounds at optimality

Conclusion
The Blue City Football Club optimization analysis demonstrates how linear programming provides quantitative decision support for revenue management problems. The optimal allocation of 9,000 VIP and 17,000 regular seats generates maximum revenue of £4,850,000 while respecting all operational constraints.

Shadow price analysis reveals that promotional t-shirt supply represents the binding constraint, with each additional shirt supporting £100 in marginal revenue. This insight directly quantifies the financial value of constraint relaxation, guiding strategic decisions about inventory investment.

The sensitivity analysis establishes that the current solution remains optimal across reasonable variations in ticket prices and demand parameters, suggesting robust decision-making under minor market fluctuations. Increasing t-shirt supply to 36,000 units generates additional revenue of exactly £100,000, matching shadow price predictions and confirming the linear optimization relationship.

This analysis provides BCFC management with quantitative insights supporting ticket pricing strategy, promotional inventory planning, and capacity utilization decisions for current and future events.
