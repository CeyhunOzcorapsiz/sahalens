# SahaLens

**A local football video analysis and tactical meeting studio.**

**English** | [Türkçe](README.tr.md)

SahaLens is a non-commercial research project helping amateur and semi-professional football teams turn match footage into event suggestions, clips and understandable reports. Its core workflow is **video → AI suggestions → review → clips → team meeting**.

This is the public product showcase. Application source code is maintained in a private repository. This repository does not distribute the application, model weights, match footage or user data.

## Screenshots

These screenshots were captured from the running application using its built-in **fictional demo match**. They illustrate the interface, not measured results from a real match or evidence of model accuracy. No broadcast footage or real player imagery is included.

**Interface language:** The application currently uses Turkish. An English interface and a language selector are not implemented. This English README documents the product; screenshots show the current Turkish interface.

### Match studio
![Match studio with fictional demo data](assets/studio.png)

### Event log
![Timestamped event log with fictional demo data](assets/events.png)

### AI suggestion review
![AI suggestion review queue with fictional demo data](assets/review.png)

### Reports and statistics
![Match report with fictional demo data](assets/stats.png)

## What has been built?

| Area | Capabilities |
| --- | --- |
| Match workspace | Matches, squads, timestamped events, local persistence and backups |
| Broadcast analysis | Temporal event spotting, scoreboard and match-clock OCR, suggestion review queue |
| Computer vision | Player and ball detection, tracking and pitch calibration research |
| Tactical analysis | 2D pitch, passing networks, video annotations and set-piece planning |
| Reporting | Shot-location-based expected goals (xG), match narratives, player and opponent reports |
| Team meetings | Event-based clip playlists, presentation view, video exports and printable reports |
| Quality controls | Data provenance, experimental-result labels and metric quality gates |

These are implemented modules, not a claim that every AI output has been validated across every broadcast format.

## Technology stack

| Layer | Technologies and purpose |
| --- | --- |
| Frontend | JavaScript, HTML, CSS and Canvas for the tactical pitch, charts and annotations |
| Local backend | Node.js HTTP server, file-based workspace storage and analysis job queue |
| AI and vision | Python, PyTorch, Ultralytics YOLO, OpenCV, NumPy and SciPy |
| Event spotting | ResNet features, temporal convolutions, Transformer and model ensemble |
| Voice notes | Local speech transcription with faster-whisper |
| Quality assurance | ESLint, Node test runner, Python unittest, Playwright, axe-core and GitHub Actions |

## How it works

1. Open a local match video in the browser-based studio.
2. Run the local Python analysis pipeline to generate event suggestions.
3. Review suggestions with timestamps and available evidence.
4. Organize reviewed events into clips and tactical reports.
5. Present selected moments in a team meeting.

## Research status

Event detection, team assignment and consistent player identities remain active research areas. Coordinate-dependent statistics require reliable tracking and pitch calibration.

Earlier experiment records report approximately **0.498 loose mAP on the SoccerNet test set**. This is not 49.8% overall accuracy and does not establish equivalent performance on new broadcasts. Recorded real-broadcast evaluations revealed substantial calibration and team-assignment limitations. Training and benchmarks were not rerun when preparing this showcase.

## Data and privacy

Core video processing runs locally. Optional external-service features require separate consideration of their data flows; this is not a blanket claim that every feature works offline. SoccerNet, StatsBomb and other third-party research resources remain subject to their respective access and licensing terms. Their datasets and model weights are not redistributed here.

## Further information

- [Architecture](docs/ARCHITECTURE.en.md)
- [Research roadmap](docs/ROADMAP.en.md)
- [Showcase materials notice](NOTICE.en.md)

Prepared on 1 November 2026 from the source code and research records inspected at that time.
