#include "shell.h"

#define MAX_COMMAND_LENGTH 100

void run_command(char *command) {
    pid_t pid;
    int status;

    pid = fork();
    if (pid < 0) {
        perror(ERR_FORK);
        exit(1);
    } else if (pid == 0) {
        /* Child process */
        char *argv[] = {command, NULL};
        if (execve(command, argv, environ) == -1) {
            perror(ERR_PATH);
            exit(1);
        }
    } else {
        /* Parent process */
        do {
            waitpid(pid, &status, WUNTRACED);
        } while (!WIFEXITED(status) && !WIFSIGNALED(status));
    }
}

int main() {
    char *line;

    while (1) {
        prompt(STDIN_FILENO); /* Displaying the prompt */

        line = _getline(stdin);

        if (line == NULL) {
            /* Handle end of file (Ctrl+D) */
            printf("\n");
            break;
        }

        /* Removing the trailing newline character */
        line[strcspn(line, "\n")] = '\0';

        run_command(line);

        free(line);
    }

    return 0;
}
