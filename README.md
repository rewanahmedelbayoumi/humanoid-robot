# HUMANOID ROBOT

**Human-Centered Robotics · AI Interaction · Numerical Intelligence**

A **170 cm, human-shaped robotic research platform** designed to combine voice interaction, expressive gestures, wheeled movement, sensor feedback, and measurable numerical improvements in a modular, affordable prototype.

> **Project status:** Planning and prototyping. The dimensions and capabilities below are design targets, not verified performance results.

## The Problem

Affordable human-shaped robots often rely on pre-programmed movements, drift during motion, or provide little explanation for their actions. This project explores whether feedback control, calibration, and clear interaction states can make a low-cost robot more accurate, understandable, and safe in controlled indoor settings.

## Project Objectives

- Build a **170 cm** human-shaped body on a stable wheeled base (not a walking biped).
- Enable voice commands, speech responses, and coordinated head, jaw, and arm gestures.
- Support movement commands with wheel-encoder feedback and obstacle-aware stopping.
- Quantify errors, calibrate motion, and compare baseline versus improved performance.
- Expose robot status, telemetry, and measured results in a lightweight dashboard.
- Develop a dedicated mobile-control interface as a target extension.
- Prioritize low center of mass, emergency stopping, and controlled tests.

## Proposed Features

| System | Planned capability |
| --- | --- |
| Human–robot interaction | Voice input, speech output, greeting, pointing, listening gestures |
| Locomotion | Two-wheel differential drive with support casters |
| Perception | Ultrasonic distance sensing and obstacle stopping |
| Motor control | ESP32, wheel encoders, closed-loop PID speed control |
| Movement quality | Constrained interpolation for smooth servo motion |
| Numerical intelligence | Odometry, least-squares calibration, median filtering, error analysis |
| Observability | Telemetry logs, CSV export, Digital Twin Lite dashboard |
| Safety | Emergency stop, command allowlist, watchdog, fault states |
| Mobile control | Dedicated app/interface (planned; platform and protocol to be finalized) |

## Preliminary Physical Specifications

| Dimension | Target |
| --- | --- |
| Overall height | 170 cm |
| Head (W × H × D) | 24 × 22 × 18 cm |
| Shoulder width | 44 cm |
| Torso (W × H) | 42 × 58 cm |
| Each arm | 50 cm |
| Lower housing including base | 82 cm |
| Base footprint | 55 × 50 cm |
| Drive wheel diameter | 10–12 cm (candidate) |

These are conceptual measurements and must be validated against door clearance, motor torque, payload, and tip-over tests before full assembly.

## System Architecture

```text
Voice / Mobile Input
         |
         v
AI / Interaction Host
(STT · Intent Validation · TTS · Logging)
         |
    Restricted Commands
         |
         v
ESP32 Firmware <--- Encoders / Distance Sensors
         |
 Motor Driver / Servo Controller
         |
 Wheels · Head · Arms · Jaw
         |
         v
    Telemetry & Dashboard
```

**Architecture decision pending:** The uploaded blueprint uses an existing laptop as the Python/voice host and excludes its cost from the purchasing budget. The intended standalone version requires **onboard compute, onboard microphone and speaker, local power, and phone connectivity**. Its hardware, power budget, and costs must be confirmed before describing the prototype as fully independent.

## Numerical Methods

1. **Differential-drive odometry:** estimate linear and angular velocity from the wheels and integrate robot pose.
2. **Least-squares calibration:** fit encoder ticks to measured travel distance.
3. **PID control:** reduce wheel-speed error and improve repeatability.
4. **Smooth interpolation:** generate controlled head and arm trajectories.
5. **Median filtering:** reduce unreliable range readings.
6. **Statistical evaluation:** use MAE, RMSE, latency, and repeated trials to report performance.

## Repository Structure

```text
humanoid-robot/
├── firmware/       # ESP32 code: drivers, motors, encoders, sensors, safety
├── host/           # Voice pipeline, decision logic, API and telemetry
├── models/         # CAD, front/side drawings, dimensions, mass estimates
├── experiments/    # Calibration, measurements, datasets, plots, reports
├── docs/           # Requirements, architecture, BOM, safety, test plans
├── README.md
└── .gitignore
```

## Implementation Roadmap — 21 Days

| Days | Shared milestone |
| --- | --- |
| 1–3 | Freeze requirements, orthographic views, mass budget, component feasibility |
| 4–6 | Bench-test motors, electronics, encoders, power protection, and emergency stop |
| 7–9 | Prototype wheeled base, firmware state machine, telemetry |
| 10–12 | Motion calibration, PID, and initial numerical comparisons |
| 13–15 | Lightweight body, head and gesture system; verify mechanical stability |
| 16–18 | Voice interaction, host integration, dashboard, mobile-control prototype |
| 19–21 | Full integration, fault tests, repeated experiments, final documentation |

All **six team members work concurrently**, with mechanical, embedded, control, AI/voice, numerical research, and integration/dashboard responsibilities coordinated through issues and pull requests. Each milestone is subject to safety and hardware feasibility checks.

## Validation and Safety

- Verify rated motor torque/current against actual payload; do not rely only on stall torque.
- Keep heavy components low and test stability with incremental loads.
- Confirm fuses, power rails, battery/charger compatibility, and a working emergency stop under qualified supervision.
- Stop motors on invalid commands, sensor faults, or lost heartbeat.
- Restrict AI output to approved high-level commands; never connect free-form language directly to motor actuation.
- Record actual experiments separately from simulation data.
- Run initial movement tests slowly in a clear, controlled area.

## Success Criteria

A safe proof-of-concept that demonstrates wheeled movement, basic voice interaction, gestures, sensor-based stopping, telemetry, and documented numerical improvement against a baseline. Full navigation, load-bearing arms, and autonomous operation are **not assumed** until validated.

## Budget Note

The initial blueprint estimates hardware purchases separately from a pre-existing laptop. Transitioning to fully onboard AI/voice processing may change the bill of materials and total cost.

## Project Team

Six contributors working in parallel across mechanical design, embedded systems, control, AI and speech, numerical methods, and software integration.

---

**Research prototype — specifications may change after testing.**
