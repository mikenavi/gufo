# Chat history cache boundaries

Add optional `cache_message_boundaries` and `cache_image_boundaries` token
offsets to `TextPromptContext`. Models can identify real message starts and
the starts of messages containing images, so serving can retain useful edit
boundaries within its existing RAM budget. Offsets are ascending, refer to
the prepared prompt and must not point into indivisible input spans. Literal
control-token text in message content is not a message boundary.

Both lists default to empty, preserving existing extension behavior. Source
extensions rebuild with the updated headers.
