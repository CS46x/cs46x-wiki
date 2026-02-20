_Owner: Team | Last updated: 2026-02-19 | Status: Draft_

# Project Overview & Goals

> A one-page summary of the problem, who benefits, and what “success” looks like (a short demo checklist works well). This anchors the team and gives graders a clear lens for evaluation.

## One Page Summary 
The Classic FPS Matchmaking Platform with Chat is a cloud-hosted web/Electron application that centralizes matchmaking, lobby organization, and real-time communication for legacy first-person shooter communities (e.g., Quake series).
Today, legacy FPS players rely on fragmented tools such as Discord, outdated server browsers, and forum posts to coordinate matches. This project unifies identity management, lobby creation, moderation, real-time chat, and voice communication into a single scalable platform built on:
- ASP.NET Core + Identity
- SignalR (real-time text, presence, events)
- Redis (presence + matchmaking state)
- RDS MySQL (durable storage)
- MediaSoup (WebRTC SFU for voice)
- AWS ECS Fargate infrastructure
The goal is to reduce coordination overhead, improve match quality, and strengthen under-supported gaming communities through an integrated system.

## Problem
Legacy FPS communities lack:
- Integrated matchmaking
- Skill-balanced grouping
- Centralized moderation
- Built-in real-time voice
- Persistent identity and session management
Players currently stitch together multiple disconnected tools, creating confusion, coordination friction, and poor match quality.

## Who Benefits
- Legacy FPS players who want organized matchmaking
- Community moderators who need enforceable moderation tools
- Small gaming communities that lack modern infrastructure
- Competitive players who value fair matches and voice coordination

## What Success Looks Like
Success is defined as:
- Users can register, log in, and maintain secure sessions
- Players can join game-specific lobbies and sub-rooms
- Real-time chat and presence updates work under load
- Players can ready-up and launch matches
- Matchmaking respects MMR and latency constraints
- Voice chat works in sub-rooms via SFU architecture
- Moderation (kick, mute, ban) works with audit logging
- Reconnection windows prevent ghost players or broken sessions
- System runs in AWS ECS with Redis-backed scale-out
Alpha success criteria:
- Full flow demo: Login → Lobby → Sub-room → Ready → Launch → Voice active

## Short Demo Checklist
- User registers and logs in
- User joins a game lobby
- User joins or creates a sub-room
- Ready-up system works
- Moderator launches match
- match.found event delivered via SignalR
- Voice chat activates in sub-room
- Reconnection within allowed window works
- Moderation action (kick or mute) propagates in real time

