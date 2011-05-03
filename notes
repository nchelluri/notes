#!/bin/bash
#
# Notes!!!
#

NOTES_DIR=~/.notes

notes() {
  _find_notes
  for i in "${NOTES[@]}"
  do
      echo "$i"
  done
}

note() {
    if [ -e "$NOTES_DIR/$1.txt" ]
    then
        cat $NOTES_DIR/$1.txt
    else
        notes
    fi
}

new-note() {
    edit-note $1
}

edit-note() {
    emacs $NOTES_DIR/$1.txt
}

_find_notes() {
    NOTES=()
    for i in `(find $NOTES_DIR -name '*.txt')`
    do
        NOTES=("${NOTES[@]}" "`basename $i .txt`")
    done
}

_note_complete() {
    local cur prev opts
    _find_notes
    COMPREPLY=()
    cur="${COMP_WORDS[COMP_CWORD]}"
    prev="${COMP_WORDS[COMP_CWORD-1]}"
    opts="${NOTES[@]}"
    COMPREPLY=( $(compgen -W "${opts}" -- ${cur}) )
    return 0
}

complete -F _note_complete note
complete -F _note_complete edit-note
