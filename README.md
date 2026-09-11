# IRP Suction Calculator

A physics-based calculator estimating the Neptune suction pressure needed to maintain a target intrarenal pressure (IRP) during ureteroscopy, based on scope/sheath geometry and irrigation pressure.

**Live: https://irpcalculator.github.io/display/**

## How it works

The model treats inflow (through the scope's working channel) and outflow (through the annular gap between scope and sheath) as laminar Poiseuille flow, and solves for the suction pressure that balances the two at a target IRP. A clinical safety factor (default 1.5×) is applied to the theoretical result to account for real-world non-idealities.

## Known limitations

- **Steady-state only.** The model assumes equilibrium has been reached. It does not capture the time lag caused by tubing dead space, compliant tubing walls, or trapped air before that equilibrium is achieved — real-world pressure response to a dial change will be slower than the model implies.
- **Suction tubing resistance not modeled.** The outflow resistance term currently only accounts for the sheath length/diameter. In reality, suction tubing runs in series between the sheath and the Neptune canister and adds its own resistance, which would reduce the required suction setting relative to this model's estimate. This is a planned addition.
- **Trapped air / compressibility.** Air in the suction line acts as compliance rather than a rigid conduit, which can cause measured pressure at the canister to lag or under-represent true pressure at the kidney. Not currently modeled.
- **Idealized geometry.** Assumes concentric, straight, non-deflected scope position within the sheath. Real eccentric positioning, debris, and scope deflection can meaningfully change the annular flow factor (potentially 20–40% higher resistance in practice).
- **Validated in only one of four tested benchtop configurations.** In benchtop testing, calculator agreement with measured suction was adequate for a HugeMed/8.5-Fr configuration (R²=0.75, MAE=15.6 mmHg) but poor for Richard Wolf 10-Fr and 11-Fr sheath configurations. Larger annular gaps showed weaker agreement, consistent with possible non-laminar flow at larger gap sizes.
- **This is a decision aid, not a validated clinical device.** We do not recommend relying on this calculator alone to determine safe suction parameters. Always verify suction settings under real operating conditions.

## Contributing

Feedback and PRs welcome, especially around adding tubing-resistance modeling.
