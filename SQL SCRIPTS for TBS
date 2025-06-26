use TicketBookingSystem
select * from Booking
select * from Customer
select * from Event
select * from Venue

alter table Booking
Alter column booking_id INT
identity(1,1);

  // 9.3 Book Tickets
        public void BookTickets(string eventName, int numTickets, string customerName)
        {
            using (SqlConnection con = DBUtil.GetDBConn())
            {
                string selectQuery = $"SELECT available_seats, ticket_price FROM Event WHERE event_name = '{eventName}'";
                SqlCommand cmd = new SqlCommand(selectQuery, con);
                SqlDataReader reader = cmd.ExecuteReader();

                if (reader.Read())
                {
                    int available = (int)reader["available_seats"];
                    decimal price = (decimal)reader["ticket_price"];
                    reader.Close();

                    if (available >= numTickets)
                    {
                        string insertBooking = $"INSERT INTO Booking (  num_tickets, total_cost, booking_date) VALUES ({numTickets}, {numTickets * price}, GETDATE())";
                        SqlCommand cmd2 = new SqlCommand(insertBooking, con);
                        cmd2.ExecuteNonQuery();

                        string updateSeats = $"UPDATE Event SET available_seats = available_seats - {numTickets} WHERE EventName = '{eventName}'";
                        SqlCommand cmd3 = new SqlCommand(updateSeats, con);
                        cmd3.ExecuteNonQuery();

                        Console.WriteLine("Booking successful.");
                    }
                    else
                    {
                        Console.WriteLine("Insufficient seats available.");
                    }
                }
                else
                {
                    Console.WriteLine("Event not found.");
                }
            }
        }

public void BookTickets(string eventName, int numTickets, string customerName)
        {
            using (SqlConnection con = DBUtil.GetDBConn())
            {
                string selectQuery = $"SELECT available_seats, ticket_price FROM Event WHERE event_name = '{eventName}'";
                SqlCommand cmd = new SqlCommand(selectQuery, con);
                SqlDataReader reader = cmd.ExecuteReader();

                if (reader.Read())
                {
                    int available = (int)reader["available_seats"];
                    decimal price = (decimal)reader["ticket_price"];
                    reader.Close();

                    if (available >= numTickets)
                    {
                        string insertBooking = $"INSERT INTO Booking (  num_tickets, total_cost, booking_date) VALUES ({numTickets}, {numTickets * price}, GETDATE())";
                        SqlCommand cmd2 = new SqlCommand(insertBooking, con);
                        cmd2.ExecuteNonQuery();

                        string updateSeats = $"UPDATE Event SET available_seats = available_seats - {numTickets} WHERE EventName = '{eventName}'";
                        SqlCommand cmd3 = new SqlCommand(updateSeats, con);
                        cmd3.ExecuteNonQuery();

                        Console.WriteLine("Booking successful.");
                    }
                    else
                    {
                        Console.WriteLine("Insufficient seats available.");
                    }
                }
                else
                {
                    Console.WriteLine("Event not found.");
                }
            }
        }
