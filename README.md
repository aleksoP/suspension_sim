# AMR Suspension Lab

Open `amr_suspension_sim_v01.html` in a modern browser. It has two complementary stages:

- **Single-wheel simulator** — screens vertical response of one trailing-arm-style
  wheel station against bumps, holes, and washboard terrain. It resolves chassis
  heave, chassis pitch, and arm rotation; pitch is restrained to represent the
  rest of the AMR’s wheel stations.
- **Design editor** — opened with **Design editor** below the simulator. It is a
  2D layout canvas for suspension concepts before selecting a wheel station for
  the simulator.

## Design editor controls

Choose a tool in the left palette, then click in the canvas:

- **Wheel**, **Pivot point**, **Free attachment**, and **Payload weight** place
  components.
- **Rigid link** and **Spring / damper** can connect any two canvas locations.
  When an endpoint is not on a component, the editor creates a free attachment
  point automatically.
- **Select / move** lets you drag components; their connected links and springs
  follow automatically.
- Select a wheel, weight, or spring to adjust its diameter, mass, or rate in
  the inspector. Use `Delete`/`Backspace` to remove the selected component.

The editor loads an AMR starter sketch with three wheel stations and a 150 kg
payload. It can be cleared or restored from the inspector.

The editor describes topology and nominal component properties only. It does
not yet solve arbitrary mechanisms; the single-wheel simulation remains the
current dynamics model.

Made for suspension geometry design.
