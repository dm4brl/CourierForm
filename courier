import React, { Component } from 'react';
import axios from 'axios';

class CourierForm extends Component {
  constructor() {
    super();
    this.state = {
      courier: {
        courier_id: '',
        courier_name: '',
        vehicle_type: '',
        max_delivery_distance_km: 0,
        working_hours: {
          start_time: '',
          end_time: ''
        },
        location: {
          latitude: 0,
          longitude: 0
        },
        status: 'available'
      }
    };
  }

  handleChange(event, field) {
    const { courier } = this.state;
    courier[field] = event.target.value;
    this.setState({ courier });
  }

  handleSubmit(event) {
    event.preventDefault();
    axios.post('/update_courier_info', this.state.courier)
      .then(response => {
        console.log('Courier information updated:', response.data);
      })
      .catch(error => {
        console.error('Failed to update courier information:', error);
      });
  }

  render() {
    const { courier } = this.state;

    return (
      <div>
        <h2>Courier Information Form</h2>
        <form onSubmit={(event) => this.handleSubmit(event)}>
          <div>
            <label>Courier ID:</label>
            <input type="text" value={courier.courier_id} onChange={(event) => this.handleChange(event, 'courier_id')} />
          </div>
          <div>
            <label>Courier Name:</label>
            <input type="text" value={courier.courier_name} onChange={(event) => this.handleChange(event, 'courier_name')} />
          </div>
          {/* Другие поля формы */}
          <div>
            <button type="submit">Submit</button>
          </div>
        </form>
      </div>
    );
  }
}

export default CourierForm;
