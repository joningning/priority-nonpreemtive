# priority-nonpreemtive
Priority Nonpreemptive Scheduling algorithm where each process is assigned a priority, and the CPU selects the process with the highest priority (usually the smallest priority number) to execute first.

## Features 
- The Process class is used to define each process with attributes such as:
  - `pid`: The process ID (like "A", "B", etc.).
  - `arrival_time`: The time when the process arrives (i.e., when it’s ready to execute).
  - `burst_time`: The total time required by the process to execute (also called CPU burst time).
  - `priority`: The priority value of the process (lower values have higher priority).
  - `completion_time`, `turnaround_time`, `waiting_time`, and `start_time`: These are placeholders for the metrics we calculate during the scheduling process.

 ## calculate_priority_non_preemptive
 - This function implements the Priority Non-Preemptive Scheduling algorithm.
     -Sorting: First, we sort the processes by their arrival time so we know which processes are available for execution at any given time.
     - Ready Queue: We check which processes have arrived by the current time and add them to the ready queue.
     - Handling Idle Time: If no process has arrived by the current time, we move forward to the next available process (i.e., the earliest arrival time).
     - Selecting Process: Among the ready processes, we select the one with the highest priority (smallest priority value). This is done using the min() function.
     - Start Time & Completion Time: The start time of a process is when the CPU begins executing it, which is the current time (or the completion time of the last process). After execution, we calculate the completion time by adding the burst time to the start time.
     - Completion: Once the process is done, we remove it from the process list and add it to the completed_processes list.

  ## display_gantt_chart 
  - This function displays a Gantt chart showing the execution timeline of the processes.
  - start_times: This list contains the start times of each process.
  - process_names: This list contains the names (IDs) of the processes.
  - barh: This matplotlib function draws a horizontal bar chart where each bar represents a process. The bar's length is the burst time of the process, and its position (left edge) is the start time.
  - Text on Gantt Chart: The text shows the start time of each process on the Gantt chart.
  - Finally, the Gantt chart is displayed using `plt.show()`.

  ## print_process_summary
  - This function prints a summary of each process.
    - Process ID
    - Arrival Time
    - Burst Time
    - Priority
    - Completion Time
    - Turnaround Time
    - Waiting Time
      
  ## calculate_average_waiting_time
  - This function calculates the average waiting time across all processes
      - It sums up the waiting times of all processes and then divides by the number of processes to get the average.

  ## main 
  - The `main` function handles the user input and drives the program.
  - Input: The user is prompted to enter the number of processes and their details (arrival time, burst time, and priority).
  - Calling Functions: The function then calls the `calculate_priority_non_preemptive` function to perform the scheduling, and displays the Gantt chart and process summary.
  - Finally, it calculates and prints the average waiting time.

## User Interaction

When the program runs, the user is prompted to enter:

1. The number of processes.
2. For each process:
   - Arrival time
   - Burst time
   - Priority number

After entering all processes, the program will display:

- A Gantt chart showing execution order and completion times.
- A summary of each process's metrics.
- The average waiting time for all processes.
    
