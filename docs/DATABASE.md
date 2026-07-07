# STUDIFY AI Database Schema

## Overview

Database: PostgreSQL (Supabase)

Authentication: Supabase Auth

Every table is connected to the authenticated user.

---

# Users

Managed by Supabase Auth

Additional Profile Table

profiles

id
name
email
avatar_url
college
course
semester
created_at

---

# Subjects

subjects

id
user_id
name
faculty
credits
color
attendance
created_at

---

# Tasks

tasks

id
user_id
title
description
subject_id
priority
status
due_date
created_at

Priority

Low

Medium

High

Urgent

Status

Todo

In Progress

Completed

---

# Notes

notes

id
user_id
subject_id
title
content
summary
created_at
updated_at

---

# Attendance

attendance

id
user_id
subject_id
present
absent
percentage
updated_at

---

# Exams

exams

id
user_id
subject_id
title
exam_date
location
created_at

---

# Events

events

id
user_id
title
description
event_date
location
created_at

---

# Study Sessions

study_sessions

id
user_id
subject_id
duration
date
pomodoro_count

---

# Flashcards

flashcards

id
user_id
note_id
question
answer

---

# AI Chats

ai_chats

id
user_id
prompt
response
created_at

---

# AI Files

ai_files

id
user_id
file_name
file_url
summary
created_at

---

# Notifications

notifications

id
user_id
title
message
is_read
created_at

---

# Settings

settings

id
user_id
theme
notifications_enabled
language
created_at

---

# Relationships

User

↓

Subjects

↓

Tasks

↓

Notes

↓

Flashcards

User

↓

Attendance

↓

Analytics

User

↓

AI Chat

↓

AI Files

---

# Storage

Supabase Storage

Folders

avatars/

notes/

pdfs/

images/

documents/

---

# Security

Row Level Security enabled

Every user only accesses their own data.

Authentication required for every request.