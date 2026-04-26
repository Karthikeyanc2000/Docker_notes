FROM python:3.11-slim
# We can use Ubuntu or Debian-based images, but they are larger. The slim variant is smaller and sufficient for our needs.

WORKDIR /app

COPY requirements.txt /app
RUN pip install --no-cache-dir -r requirements.txt

COPY devops /app/devops
# COPY behavior depends on SOURCE, not destination.

# COPY devops /app/devops
# → Copies the entire "devops" folder into /app/devops

# COPY devops /app
# → Also results in /app/devops (folder preserved)

# COPY devops/ /app
# → Copies only the contents inside "devops" into /app (no outer folder)

# COPY devops .
# → Same as COPY devops /app (since WORKDIR=/app), so folder is preserved
WORKDIR /app/devops

EXPOSE 8000

# ENTRYPOINT defines the main executable that always runs (python3).
# CMD provides default arguments to the ENTRYPOINT and can be overridden at runtime.
# ENTRYPOINT is optional; we can use only CMD, but then the entire command can be overridden.
# Using ENTRYPOINT + CMD allows fixing the main command while keeping arguments flexible.
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]

# -------------------------------
# 🔥 DEBUGGING NOTES (VERY IMPORTANT)
# -------------------------------

# If container fails, inspect file structure:
# docker run -it --entrypoint /bin/bash <image_name>

# Then check:
# ls /app
# ls /app/devops

# Exit container:
# Ctrl + D

# -------------------------------
# 🔥 DOCKER CACHE NOTE
# -------------------------------

# Docker may reuse cached layers even after changes
# Cache depends on Dockerfile steps and file changes (NOT tag)

# To force fresh build:
# docker build --no-cache -t <image_name> .