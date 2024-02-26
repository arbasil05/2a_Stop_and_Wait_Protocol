# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
import time
import random

def send_frame(frame):
    print(f"Sending frame: {frame}")
    time.sleep(1)  # Simulating transmission delay
    return True  # Simulating successful transmission

def receive_ack():
    time.sleep(1)  # Simulating transmission delay
    return random.choice([True, False])  # Simulating ACK loss with 50% probability

def stop_and_wait(frame_size):
    frames_sent = 0
    while frames_sent < frame_size:
        frame = f"Frame {frames_sent}"
        ack_received = False
        while not ack_received:
            if send_frame(frame):
                ack_received = receive_ack()
                if ack_received:
                    print("ACK received")
                    frames_sent += 1
                else:
                    print("Timeout! Resending frame...")
            else:
                print("Transmission failed! Resending frame...")

if __name__ == "__main__":
    frame_size = int(input("Enter the number of frames to send: "))
    stop_and_wait(frame_size)

```
## OUTPUT
![image](https://github.com/arbasil05/2a_Stop_and_Wait_Protocol/assets/144218037/1c70f7c2-ced2-46f7-9ea8-ce8a443e05ae)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
