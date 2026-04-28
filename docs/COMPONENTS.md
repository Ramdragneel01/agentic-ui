# Component API Summary

## StreamingMessage

Props:
- `role`: `assistant | user | system`
- `content`: message text
- `isStreaming`: token reveal mode
- `revealIntervalMs`: reveal speed
- `ariaLabel`: optional accessibility label

## ToolCallVisualizer

Props:
- `calls`: list of tool call items
- `title`: optional section title

## AgentTraceTimeline

Props:
- `events`: ordered trace events
- `title`: optional section title

## ConfidenceMeter

Props:
- `value`: confidence from 0 to 1
- `label`: meter label
- `warningThreshold`: warning boundary
- `goodThreshold`: good boundary

## ThinkingIndicator

Props:
- `active`: shows animated status when true
- `label`: screen-reader and visible status text
