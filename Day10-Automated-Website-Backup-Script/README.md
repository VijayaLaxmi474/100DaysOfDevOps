#!/bin/bash

SRC_DIR="/var/www/html/blog"
TMP_BACKUP="/backup"
BACKUP_FILE="xfusioncorp_blog.zip"
REMOTE_USER="clint"
REMOTE_HOST="stbkp01"
REMOTE_DIR="/backup"

# Create the zip archive
zip -r "${TMP_BACKUP}/${BACKUP_FILE}" "${SRC_DIR}"

# Verify the zip file exists before copying
if [ -f "${TMP_BACKUP}/${BACKUP_FILE}" ]; then
    scp "${TMP_BACKUP}/${BACKUP_FILE}" ${REMOTE_USER}@${REMOTE_HOST}:${REMOTE_DIR}/
else
    echo "Backup file not found! Something went wrong with the zip command."
fi
