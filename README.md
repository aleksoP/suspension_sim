# AMR Suspension Lab

Open `amr_suspension_sim_v01.html` in a modern browser. It has two complementary stages:

- **Single-wheel simulator** — screens vertical response of one trailing-arm-style
  wheel station against bumps, holes, and washboard terrain. It resolves chassis
  heave, chassis pitch, and arm rotation; pitch is restrained to represent the
  rest of the AMR’s wheel stations.
- **Design editor** — opened with **Design editor** below the simulator. It is a
  2D layout canvas for suspension concepts before selecting a wheel station for
  the simulator.
- **Whole-vehicle concept test** — builds a moving planar test directly from
  the editor layout. It runs over fixed terrain using driven and passive wheels,
  rigid-link constraints, spring/damper forces, and payload mass.

## Design editor controls

Choose a tool in the left palette, then click in the canvas:

- **Chassis body** places a rigid mass carrier. Click its face with a Link or
  Spring tool to create a body-mounted attachment point; these attachments move
  with the body.
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

## From chassis layout to vehicle test

1. Open the **Design editor** and load the AMR starter or create a side profile.
2. Add at least two wheels, connect the chassis with rigid links and springs,
   and place one or more payload weights.
3. Select a wheel and enable **Driven wheel** in its inspector. Other wheels
   remain passive.
4. Set terrain, test speed, bump/hole dimensions, and payload values in the
   controls above.
5. Press **Run vehicle test** in the editor.

The test reports forward progress, structural-link pitch, minimum clearance,
wheel contacts, and screening outcomes such as chassis strike, pitch-over, or
low-traction/stuck behavior. A teal wheel hub indicates a driven wheel; a teal
rim indicates ground contact.

This is a 2D, longitudinal concept screen. It is suitable for comparing early
layouts and identifying obvious clearance, contact, and pitch problems. It is
not a replacement for a validated tire model, structural analysis, or 3D roll-
over simulation. The editor’s shared node/link/spring data model is intended
to become the input to a later MuJoCo/Project Chrono backend.

Made for suspension geometry design.
