+++
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
date = {{ .Date }}
draft = true
tags = []
summary = ''

# Set true if this post was drafted or substantially edited with AI help.
# Renders "Written with LLM assistance" under the title and the note below
# as a Disclaimer section at the end of the post.
assisted = false

# Say what the LLM ACTUALLY did on this specific post -- what it was asked to
# dig up, what it drafted, what it got wrong, what stayed mine.
# Written in first person: "I" is me, the LLM is "it", never "we".
# Boilerplate defeats the point. Markdown is allowed.
assisted_note = """
"""
+++
