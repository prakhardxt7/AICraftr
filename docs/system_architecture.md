Nodes: Ingestor → Fetch/Clean → Summarizer → Router → Writer
→ Critique → Rewriter (loop ≤ 3) → Compliance → Auto-Publish → PostLog
                            ↘ (if fail) Review Queue (HITL)
Memory: Brand Voice Memory (feedback & edits), used by Summarizer/Writer
Observability: Tracing + Metrics (LangSmith; later Prometheus)
